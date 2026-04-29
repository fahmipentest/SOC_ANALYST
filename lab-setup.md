# 🔬 Home Lab Setup — SOC Analyst

Panduan membangun home lab SOC analyst menggunakan Proxmox (yang sudah kamu pelajari di bootcamp X-code).

---

## 🖥️ Spesifikasi Minimum

| Komponen | Minimum | Rekomendasi |
|---|---|---|
| RAM | 16 GB | 32 GB |
| Storage | 500 GB HDD | 1 TB SSD |
| CPU | 4 core | 8 core |
| OS Host | Proxmox VE | Proxmox VE |

---

## 🏗️ Arsitektur Lab

```
[Proxmox Host]
│
├── VM 1: pfSense / MikroTik (Router/Firewall)
│   └── Mengatur traffic antar segment
│
├── VM 2: Wazuh SIEM (Manager + Dashboard)
│   └── Menerima logs dari semua VM
│
├── VM 3: ELK Stack (Elasticsearch + Kibana)
│   └── Log aggregation & visualization
│
├── VM 4: Windows Server 2019 (Active Directory)
│   └── Target untuk simulasi AD attacks
│
├── VM 5: Ubuntu Server (Web Server)
│   └── Nginx + DVWA untuk web attack simulation
│
└── VM 6: Kali Linux (Attacker machine)
    └── Untuk generate attack traffic dan test detection
```

---

## ⚡ Quick Start: Deploy Wazuh di Proxmox

```bash
# Di VM Ubuntu Server (min 4GB RAM, 50GB disk)

# 1. Update sistem
sudo apt update && sudo apt upgrade -y

# 2. Install Wazuh (all-in-one)
curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh
sudo bash wazuh-install.sh -a

# 3. Akses dashboard
# https://[IP_VM]:443
# User: admin
# Password: (ditampilkan setelah install)
```

---

## 📥 Install Wazuh Agent di Windows

```powershell
# Download dan install agent
Invoke-WebRequest -Uri https://packages.wazuh.com/4.x/windows/wazuh-agent-4.7.0-1.msi -OutFile wazuh-agent.msi
msiexec.exe /i wazuh-agent.msi /q WAZUH_MANAGER="[IP_WAZUH_SERVER]"

# Start service
NET START WazuhSvc
```

---

## 🎯 Skenario Practice yang Direkomendasikan

### Skenario 1: Brute Force SSH
1. Dari Kali Linux, jalankan: `hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://[IP_UBUNTU]`
2. Pantau alert di Wazuh dashboard
3. Buat correlation rule untuk block IP setelah 5 failed attempt

### Skenario 2: Web Application Attack
1. Install DVWA di Ubuntu Server
2. Dari Kali, lakukan SQL Injection menggunakan SQLMap
3. Aktifkan ModSecurity WAF
4. Pantau detection di Wazuh + Nginx logs

### Skenario 3: Windows Lateral Movement
1. Setup Windows Server dengan Active Directory
2. Dari Kali, gunakan Impacket untuk simulate Pass-the-Hash
3. Monitor Event ID 4624 (Logon Type 3 + NTLM) di Wazuh
4. Buat alert rule untuk deteksi

### Skenario 4: Malware Simulation (Safe)
1. Download sample dari MalwareBazaar (JANGAN di mesin production!)
2. Analisis di Any.run terlebih dahulu
3. Extract IOC (hash, IP, domain)
4. Buat YARA rule berdasarkan pattern yang ditemukan
5. Test YARA rule di VM isolated

---

## 📊 Tips Dokumentasi Lab

Setiap skenario yang kamu practice, dokumentasikan dengan format:

```markdown
## [Nama Skenario]
**Tanggal:** YYYY-MM-DD
**Attack Technique:** MITRE ATT&CK T[XXXX]
**Tools:** [daftar tools]

### Setup
[Langkah setup environment]

### Attack Execution
[Command yang digunakan]

### Detection
[Alert yang muncul di SIEM, log yang relevan]

### Response
[Langkah investigasi dan containment]

### Lessons Learned
[Apa yang dipelajari, improvement untuk rule]
```

Upload writeup ini ke folder `/writeups` di GitHub kamu!

---

*Lab yang konsisten digunakan > lab yang bagus tapi jarang dibuka* 🔬
