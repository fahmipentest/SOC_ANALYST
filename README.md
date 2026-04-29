# 🛡️ SOC / Cybersecurity Analyst — Complete Skill Roadmap

> Panduan lengkap 76 poin skill untuk menjadi SOC Analyst, disusun berdasarkan standar industri 2025–2026.  
> Dibuat oleh **Fahmi Riansyah** | Penetration Tester | Tangerang, Indonesia

[![PDF Guide](https://img.shields.io/badge/📄_Download-PDF_Guide-blue?style=for-the-badge)](./SOC_Analyst_Skill_Guide.pdf)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin)](https://linkedin.com/in/fahmipentest)
[![GitHub](https://img.shields.io/badge/GitHub-fahmipentest-181717?style=for-the-badge&logo=github)](https://github.com/fahmipentest)

---

## 📌 Tentang Repositori Ini

Repositori ini berisi **roadmap lengkap** yang saya buat sebagai panduan belajar menuju posisi SOC Analyst / Cybersecurity Analyst.

Semua materi diorganisasikan berdasarkan **pengalaman nyata di industri** dan saya gunakan secara pribadi untuk tracking progress belajar.

Kamu bebas menggunakan, fork, dan memodifikasi untuk kebutuhanmu sendiri.

---

## 📊 Ringkasan

| Kategori | Jumlah Poin | Fokus Utama |
|---|---|---|
| 🌐 Networking Fundamentals | 10 poin | OSI, TCP/IP, DNS, Firewall |
| 💻 OS & Sysadmin | 12 poin | Linux CLI, Windows Event Log, AD |
| 📡 SIEM & Log Monitoring | 11 poin | Splunk, ELK, Wazuh, Log Sources |
| 🎯 Threat Intelligence & IR | 16 poin | MITRE ATT&CK, Kill Chain, IOC |
| 🔧 Tools Praktis | 15 poin | Wireshark, Volatility, YARA |
| 📝 Soft Skills & Sertifikasi | 12 poin | IR Report, Playbook, CompTIA |
| **Total** | **76 poin** | |

### Level Badge

| Badge | Keterangan |
|---|---|
| 🟢 `WAJIB` | Harus dikuasai sebelum apply SOC Analyst |
| 🔵 `NICE TO HAVE` | Nilai tambah, meningkatkan peluang lolos |
| 🟠 `ADVANCED` | Senior-level, untuk growth jangka panjang |

---

## 🗺️ Roadmap Visual

```
FASE 1 — Fondasi (0–3 Bulan)
├── ✅ Networking: OSI, TCP/IP, Subnetting, Port/Protocol
├── ✅ Linux CLI & Log Management
├── ✅ Windows Event Log & Active Directory
└── ✅ TryHackMe SOC Level 1 Path

FASE 2 — SIEM & Tools (3–6 Bulan)
├── ✅ Splunk (Free Course + Core Certified User Exam)
├── ✅ Elastic Stack / ELK
├── ✅ Wireshark & tcpdump (daily practice)
├── ✅ MITRE ATT&CK & Cyber Kill Chain
└── ✅ CompTIA Security+ (preparation)

FASE 3 — Sertifikasi & Apply (6–12 Bulan)
├── ✅ CompTIA Security+ (exam)
├── ✅ CompTIA CySA+ (exam)
├── ✅ Build 2–3 IR writeup di blog/GitHub
└── ✅ Apply SOC Analyst L1 / Junior Security Analyst
```

---

## 📚 Detail Skill per Kategori

---

### 1. 🌐 Networking Fundamentals

> Fondasi paling krusial. Setiap alert di SIEM akan melibatkan IP, port, protokol, dan traffic pattern.

| # | Skill | Level | Penjelasan |
|---|---|---|---|
| 1 | OSI Model & TCP/IP Stack | 🟢 WAJIB | Layer 1–7, fungsi masing-masing. Pahami di layer mana serangan terjadi |
| 2 | Protokol Jaringan Utama | 🟢 WAJIB | HTTP/S, DNS, DHCP, FTP, SSH, SMTP, ARP, ICMP — cara kerja & abuse-nya |
| 3 | Subnetting & CIDR Notation | 🟢 WAJIB | Hitung subnet manual. Pahami IP private (RFC1918) vs public |
| 4 | Port & Service Mapping | 🟢 WAJIB | Hafal: 21(FTP), 22(SSH), 25(SMTP), 53(DNS), 80(HTTP), 443(HTTPS), 445(SMB), 3389(RDP) |
| 5 | TCP 3-Way Handshake & Flags | 🟢 WAJIB | SYN, SYN-ACK, ACK, FIN, RST — bisa baca di Wireshark |
| 6 | Firewall, IDS & IPS | 🟢 WAJIB | Stateful vs stateless. Signature-based vs anomaly-based detection |
| 7 | DNS Resolution Process | 🟢 WAJIB | Recursive vs iterative query. DNS poisoning, hijacking, tunneling |
| 8 | VPN & Tunneling | 🔵 NICE | IPSec, SSL VPN. Bagaimana attacker sembunyikan traffic via tunnel |
| 9 | Proxy & Reverse Proxy | 🔵 NICE | Forward/reverse proxy, transparent proxy, anomali via proxy logs |
| 10 | Network Segmentation & VLAN | 🟠 ADVANCED | DMZ, internal zone, guest zone, zero-trust network concept |

---

### 2. 💻 Operating System & Sysadmin

> Harus bisa navigasi Linux dan Windows seperti rumah sendiri. Sebagian besar investigasi SOC dimulai dari log OS.

#### Linux

| # | Skill | Level | Penjelasan |
|---|---|---|---|
| 11 | Command Line Dasar | 🟢 WAJIB | `ls`, `grep`, `awk`, `sed`, `find`, `ps`, `netstat`, `lsof` — wajib hafal & lancar |
| 12 | Log Management Linux | 🟢 WAJIB | `/var/log/` structure: `auth.log`, `syslog`, `kern.log`, `access.log` |
| 13 | User & Permission Management | 🟢 WAJIB | `chmod`, `chown`, `sudo`, `/etc/passwd`, `/etc/shadow` — deteksi privesc |
| 14 | Process & Service Monitoring | 🟢 WAJIB | `ps aux`, `top`, `htop`, `systemctl`, `crontab`. Identifikasi proses mencurigakan |
| 15 | Bash Scripting Dasar | 🔵 NICE | Loop, kondisi, parsing log otomatis. Contoh: extract IP dan cek reputasi |
| 16 | File Integrity & Hashing | 🔵 NICE | `md5sum`, `sha256sum`, tripwire. Deteksi perubahan file tidak sah |

#### Windows

| # | Skill | Level | Penjelasan |
|---|---|---|---|
| 17 | Windows Event Log & Event ID | 🟢 WAJIB | **4624** Logon, **4625** Failed, **4648** Explicit Creds, **4688** New Process, **4698** Sched Task, **4720** New User, **7045** New Service |
| 18 | Active Directory Fundamentals | 🟢 WAJIB | Domain, OU, GPO, user/group, Kerberos, trust — punya offensive background? Ini sudah kamu kuasai! |
| 19 | Windows Registry Investigation | 🟢 WAJIB | `HKLM\...\Run` persistence locations, Autoruns analysis |
| 20 | PowerShell untuk Investigasi | 🟢 WAJIB | `Get-Process`, `Get-NetTCPConnection`, `Get-EventLog`. Deteksi encoded commands |
| 21 | Windows Defender & AV Logs | 🔵 NICE | Quarantine events, detection history, suspicious exclusion paths |
| 22 | Sysmon (System Monitor) | 🟠 ADVANCED | Event ID 1(Process), 3(Network), 11(File), 13(Registry). Config SwiftOnSecurity |

---

### 3. 📡 SIEM & Log Monitoring

> Tools inti pekerjaan SOC analyst sehari-hari. Kemampuan query SIEM adalah yang paling sering diuji saat interview.

#### Platform SIEM

| # | Skill | Level | Penjelasan |
|---|---|---|---|
| 23 | Splunk | 🟢 WAJIB | SPL query, dashboard, saved searches, correlation rules, alerts. Platform paling dominan di industri |
| 24 | Elastic Stack (ELK) | 🟢 WAJIB | Elasticsearch query DSL, Kibana dashboard, Filebeat/Logstash pipeline |
| 25 | Wazuh SIEM | 🟢 WAJIB | Rules, decoders, active response, agent management. Sudah dipelajari di bootcamp! |
| 26 | Microsoft Sentinel | 🔵 NICE | KQL (Kusto Query Language), workbooks, analytics rules, SOAR playbooks |
| 27 | IBM QRadar / ArcSight | 🔵 NICE | Enterprise tier. Cukup pahami konsep offense, rules, dan navigasi dasar |

#### Log Sources

| # | Skill | Level | Penjelasan |
|---|---|---|---|
| 28 | Windows Event Logs | 🟢 WAJIB | Security, System, Application, PowerShell Operational, Sysmon |
| 29 | Linux Syslog & Auth.log | 🟢 WAJIB | SSH login attempts, sudo usage, cron execution, service events |
| 30 | Firewall & IDS Logs | 🟢 WAJIB | Snort/Suricata alerts, MikroTik logs, pfSense. Filter by severity |
| 31 | Web Server Logs | 🟢 WAJIB | Nginx/Apache `access.log`. Deteksi SQLi, XSS, LFI dari log pattern |
| 32 | DNS Query Logs | 🔵 NICE | Deteksi C2 via DNS, DGA (Domain Generation Algorithm), DNS tunneling |
| 33 | Cloud Audit Logs | 🟠 ADVANCED | AWS CloudTrail, Azure Activity Log, GCP Audit Logs. Deteksi IAM abuse |

---

### 4. 🎯 Threat Intelligence & Incident Response

> Core knowledge untuk memahami ancaman, mengklasifikasikan insiden, dan merespons secara terstruktur.

#### Framework & Metodologi

| # | Skill | Level | Penjelasan |
|---|---|---|---|
| 34 | MITRE ATT&CK Framework | 🟢 WAJIB | 14 tactic, ratusan technique. Hafal semua tactic: Recon → Exfiltration → Impact |
| 35 | Cyber Kill Chain (Lockheed Martin) | 🟢 WAJIB | 7 tahap: Recon → Weaponization → Delivery → Exploitation → Install → C2 → Actions |
| 36 | Incident Response Lifecycle (NIST) | 🟢 WAJIB | Preparation → Detection → Containment → Eradication → Recovery → Post-Incident |
| 37 | Pyramid of Pain | 🟢 WAJIB | IOC dari terendah: Hash → IP → Domain → Network Artifact → Tool → TTP |
| 38 | Diamond Model | 🔵 NICE | 4 node: Adversary, Infrastructure, Capability, Victim — untuk attribution |
| 39 | NIST Cybersecurity Framework | 🔵 NICE | 5 function: Identify, Protect, Detect, Respond, Recover — komunikasi ke management |

#### Threat Intelligence

| # | Skill | Level | Penjelasan |
|---|---|---|---|
| 40 | IOC Types & Manual Hunting | 🟢 WAJIB | IP, domain, URL, file hash (MD5/SHA256), email header, mutex, registry key |
| 41 | Tools Enrichment IOC | 🟢 WAJIB | VirusTotal, AbuseIPDB, Shodan, URLVoid, MXToolbox, Talos Intelligence |
| 42 | OSINT Dasar | 🔵 NICE | Maltego, theHarvester, WHOIS, certificate transparency, Shodan dorks |
| 43 | Threat Intel Platforms | 🟠 ADVANCED | MISP, OpenCTI, AlienVault OTX, FS-ISAC sharing communities |

#### Pola Serangan yang Harus Dikenali

| # | Skill | Level | Penjelasan |
|---|---|---|---|
| 44 | Phishing & Email-Based Attacks | 🟢 WAJIB | Header analysis, SPF/DKIM/DMARC, URL deobfuscation, attachment analysis |
| 45 | Brute Force & Credential Stuffing | 🟢 WAJIB | Deteksi via: volume failed login singkat, multiple IP, credential reuse patterns |
| 46 | Web Application Attacks | 🟢 WAJIB | SQLi, XSS, LFI/RFI, SSRF, path traversal — deteksi dari web log. Kamu sudah ahli ini! |
| 47 | Lateral Movement Techniques | 🟢 WAJIB | Pass-the-Hash, Pass-the-Ticket, Mimikatz, WMI remote exec, PsExec, RDP abuse |
| 48 | Ransomware Behavior Patterns | 🟢 WAJIB | Mass file rename, VSS deletion, C2 beacon traffic, privilege escalation pre-encryption |
| 49 | Living off the Land (LotL) | 🔵 NICE | LOLBins: `certutil`, `bitsadmin`, `mshta`, `regsvr32`, `powershell -EncodedCommand` |

---

### 5. 🔧 Tools Praktis SOC Analyst

> Harus bisa hands-on, bukan sekadar tahu namanya. Semua tools ini bisa dipraktikkan gratis di lab sendiri.

#### Network Analysis

| # | Skill | Level | Penjelasan |
|---|---|---|---|
| 50 | Wireshark | 🟢 WAJIB | BPF filter, follow TCP/HTTP stream, detect anomali protocol, export objects |
| 51 | tcpdump | 🟢 WAJIB | Capture & filter via CLI. `tcpdump -i eth0 -w out.pcap 'port 80'` |
| 52 | Zeek (Bro) | 🔵 NICE | Network traffic analysis. Auto-generate: `conn.log`, `dns.log`, `http.log`, `ssl.log` |
| 53 | Suricata & Snort | 🔵 NICE | Deploy sebagai IDS/IPS. Baca dan tulis custom rules. Format alert output |

#### Endpoint & Memory Forensics

| # | Skill | Level | Penjelasan |
|---|---|---|---|
| 54 | Process Explorer & Autoruns | 🟢 WAJIB | Deteksi persistence, suspicious process dengan parent aneh, DLL injection |
| 55 | Any.run & Hybrid Analysis | 🟢 WAJIB | Online sandbox malware. Submit file/URL, baca behavior report — gratis! |
| 56 | Volatility Framework | 🔵 NICE | Memory forensics: `pslist`, `netscan`, `filescan`, `malfind`, `dumpfiles` |
| 57 | Autopsy / FTK Imager | 🔵 NICE | Disk forensics dasar: timeline, deleted file recovery, hash verification |
| 58 | YARA Rules | 🟠 ADVANCED | Tulis rules deteksi pattern malware di file/memory. Otomasi dengan `yara-python` |

#### Vulnerability & Recon Tools

| # | Skill | Level | Penjelasan |
|---|---|---|---|
| 59 | Nmap | 🟢 WAJIB | Host discovery, port scan, service/OS detection, NSE scripts — kamu sudah expert! |
| 60 | Nessus / OpenVAS | 🟢 WAJIB | Vulnerability scanning, baca CVSS score, false positive handling |
| 61 | Burp Suite | 🟢 WAJIB | Proxy, intercept, repeater — kamu sudah punya ini dari offensive background! |
| 62 | Metasploit (defensif) | 🔵 NICE | Pahami exploit yang dipakai attacker. Mapping ke MITRE ATT&CK technique |

---

### 6. 📝 Soft Skills, Reporting & Sertifikasi

> Menentukan karir jangka panjang. Analyst yang bisa berkomunikasi dengan baik selalu lebih diprioritaskan.

#### Documentation & Reporting

| # | Skill | Level | Penjelasan |
|---|---|---|---|
| 63 | Menulis Incident Report | 🟢 WAJIB | Executive Summary + Timeline + Technical Detail + Root Cause + Recommendation |
| 64 | Case & Ticket Management | 🟢 WAJIB | TheHive, JIRA, ServiceNow. Dokumentasi setiap langkah investigasi real-time |
| 65 | Runbook & Playbook | 🟢 WAJIB | SOP untuk tipe insiden: phishing, ransomware, DDoS, insider threat |
| 66 | Timeline Reconstruction | 🟢 WAJIB | Format: `[timestamp] [source] [event] [analyst note]` dari multiple log sources |

#### Soft Skills

| # | Skill | Level | Penjelasan |
|---|---|---|---|
| 67 | Alert Triage & Prioritization | 🟢 WAJIB | True positive vs false positive vs benign true positive. Scoring severity |
| 68 | Adversarial Mindset | 🟢 WAJIB | Berpikir seperti attacker. Offensive background adalah keunggulan besar di SOC! |
| 69 | Komunikasi Teknis ke Non-Teknis | 🟢 WAJIB | Jelaskan insiden ke management tanpa jargon. Fokus pada business impact |
| 70 | Tim Collaboration & Escalation | 🟢 WAJIB | Kapan handle sendiri vs escalate ke L2/L3 vs Incident Commander |

#### Sertifikasi Target (Urutan Prioritas)

| # | Sertifikasi | Level | Keterangan |
|---|---|---|---|
| 71 | CompTIA Security+ | 🟢 WAJIB | Entry-level, diakui global. Banyak job posting mensyaratkan ini. Prep: ~3 bulan |
| 72 | CompTIA CySA+ (CS0-003) | 🟢 WAJIB | Spesifik SOC analyst & threat intel. Lebih praktikal dari Security+. Prep: ~3 bulan |
| 73 | Blue Team Labs / TryHackMe SOC L1 | 🟢 WAJIB | Hands-on gratis, langsung bisa masuk CV sebagai portfolio |
| 74 | Splunk Core Certified User | 🔵 NICE | Course gratis di Splunk Education. Cert ~$130. Nilai tinggi di job market |
| 75 | Microsoft SC-200 | 🟠 ADVANCED | Untuk environment Microsoft/Azure. Sangat relevan untuk Sentinel & Defender |
| 76 | GCIH / GCIA (GIAC) | 🟠 ADVANCED | Gold standard SOC. Mahal (~$900) tapi prestige dan diakui enterprise global |

---

## 📁 Struktur Repositori

```
soc-analyst-roadmap/
│
├── README.md                          ← Kamu sedang membaca ini
├── SOC_Analyst_Skill_Guide.pdf        ← PDF lengkap 76 poin (printable + checkboxes)
│
├── checklist/
│   ├── 01-networking.md               ← Checklist Networking
│   ├── 02-os-sysadmin.md              ← Checklist OS & Sysadmin
│   ├── 03-siem-monitoring.md          ← Checklist SIEM & Monitoring
│   ├── 04-threat-incident.md          ← Checklist Threat Intel & IR
│   ├── 05-tools.md                    ← Checklist Tools Praktis
│   └── 06-softskills-certs.md         ← Checklist Soft Skills & Sertifikasi
│
├── resources/
│   ├── free-learning.md               ← Kumpulan resource belajar gratis
│   ├── lab-setup.md                   ← Cara setup home lab SOC
│   └── interview-prep.md              ← Pertanyaan umum interview SOC Analyst
│
└── writeups/                          ← Koleksi writeup lab & practice (coming soon)
    └── .gitkeep
```

---

## 🎓 Resource Belajar Gratis

### Platform Hands-On
| Platform | Konten | Link |
|---|---|---|
| TryHackMe | SOC Level 1 & 2 Path | [tryhackme.com](https://tryhackme.com) |
| Blue Team Labs Online | Incident Response challenges | [blueteamlabs.online](https://blueteamlabs.online) |
| LetsDefend | SOC Analyst simulation | [letsdefend.io](https://letsdefend.io) |
| CyberDefenders | Blue team CTF challenges | [cyberdefenders.org](https://cyberdefenders.org) |

### SIEM & Tools
| Resource | Konten | Link |
|---|---|---|
| Splunk Free Training | Fundamentals 1 & 2 | [education.splunk.com](https://education.splunk.com) |
| Elastic Learn | ELK Stack fundamentals | [learn.elastic.co](https://learn.elastic.co) |
| Malware Traffic Analysis | PCAP files untuk Wireshark | [malware-traffic-analysis.net](https://malware-traffic-analysis.net) |
| MITRE ATT&CK | Framework official | [attack.mitre.org](https://attack.mitre.org) |

### Sertifikasi
| Sertifikasi | Resource | Link |
|---|---|---|
| CompTIA Security+ | Professor Messer (gratis) | [professormesser.com](https://professormesser.com) |
| CompTIA CySA+ | CompTIA official study guide | [comptia.org](https://comptia.org) |
| Splunk Core User | Free on-demand training | [education.splunk.com](https://education.splunk.com) |

---

## 🧑‍💻 Tentang Saya

Saya **Fahmi Riansyah**, seorang Penetration Tester berbasis di Tangerang, Indonesia dengan spesialisasi di:

- **Web Application VAPT** — OWASP Top 10, Burp Suite, manual testing
- **Network & Infrastructure Assessment** — Nmap, Metasploit, service enumeration
- **Active Directory Attack Simulation** — Kerberoasting, Pass-the-Hash, lateral movement
- **Cloud Security** — CCSE certified, cloud misconfiguration assessment

**Sertifikasi:**
- CEH (EC-Council)
- CRTOM (Red Team Leaders)
- Certified Web Red Team Analyst
- CCSE (CyberWarfare Labs)

**Sedang dalam perjalanan menuju** SOC Analyst / Cybersecurity Analyst role, dengan mengkombinasikan offensive security background untuk keunggulan dalam threat detection dan incident response.

📧 Hubungi saya via GitHub: [@fahmipentest](https://github.com/fahmipentest)

---

## 🤝 Kontribusi

Menemukan informasi yang perlu diperbarui, atau ingin menambahkan resource yang berguna?

1. Fork repositori ini
2. Buat branch baru: `git checkout -b tambah-resource`
3. Commit perubahan: `git commit -m 'Tambah resource belajar X'`
4. Push: `git push origin tambah-resource`
5. Buat Pull Request

---

## 📄 Lisensi

Repositori ini menggunakan lisensi **MIT** — bebas digunakan, dimodifikasi, dan disebarluaskan dengan mencantumkan kredit.

---

<div align="center">

**⭐ Jika repositori ini membantu, berikan Star ya!**

*Dibuat dengan ❤️ untuk komunitas cybersecurity Indonesia*

</div>
