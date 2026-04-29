# 🎓 Resource Belajar Gratis — SOC Analyst

Kumpulan resource terbaik yang bisa kamu akses gratis (atau sangat murah) untuk mempersiapkan diri sebagai SOC Analyst.

---

## 🖥️ Platform Hands-On Practice

### TryHackMe
- **Link:** https://tryhackme.com
- **Rekomendasi Path:** SOC Level 1 → SOC Level 2
- **Biaya:** Gratis (akses terbatas) / ~$14/bulan untuk premium
- **Cocok untuk:** Belajar dari nol, guided learning, ada badge untuk CV

### Blue Team Labs Online
- **Link:** https://blueteamlabs.online
- **Rekomendasi:** Semua challenge kategori "Incident Response" dan "Threat Hunting"
- **Biaya:** Gratis
- **Cocok untuk:** Simulasi investigasi nyata, hands-on SIEM

### LetsDefend
- **Link:** https://letsdefend.io
- **Rekomendasi:** SOC Analyst learning path
- **Biaya:** Gratis (basic) / berbayar untuk fitur lengkap
- **Cocok untuk:** Simulasi pekerjaan SOC analyst sehari-hari

### CyberDefenders
- **Link:** https://cyberdefenders.org
- **Rekomendasi:** Blue team CTF challenges
- **Biaya:** Gratis
- **Cocok untuk:** Practice investigate PCAP, memory dump, log analysis

---

## 📡 SIEM Training

### Splunk (Paling Penting!)
- **Free Training:** https://education.splunk.com
  - Splunk Fundamentals 1 (gratis, online)
  - Splunk Fundamentals 2 (gratis, online)
- **Setelah training:** Ambil ujian **Splunk Core Certified User** (~$130)
- **Kenapa penting:** Splunk adalah SIEM paling populer di industri

### Elastic / ELK Stack
- **Free Training:** https://learn.elastic.co
- **Praktik langsung:** Install ELK di VM (Proxmox yang kamu sudah punya!)
- **Resource tambahan:** https://elasticstack.blog

### Wazuh
- **Dokumentasi resmi:** https://documentation.wazuh.com
- **YouTube:** Channel resmi Wazuh — banyak tutorial gratis
- **Sudah dipelajari di bootcamp X-code — manfaatkan!**

---

## 🔍 Threat Intelligence & MITRE ATT&CK

| Resource | Link | Keterangan |
|---|---|---|
| MITRE ATT&CK Official | https://attack.mitre.org | Framework, matrix, technique detail |
| ATT&CK Navigator | https://mitre-attack.github.io/attack-navigator | Visualisasi coverage |
| MITRE D3FEND | https://d3fend.mitre.org | Defensive countermeasure mapping |
| VirusTotal | https://virustotal.com | IOC lookup gratis |
| AbuseIPDB | https://abuseipdb.com | IP reputation check |
| Shodan | https://shodan.io | Internet-connected device search |
| AlienVault OTX | https://otx.alienvault.com | Community threat intel feeds |
| Any.run | https://any.run | Free malware sandbox |
| Hybrid Analysis | https://hybrid-analysis.com | Free malware analysis |

---

## 📦 PCAP & Log Files untuk Practice

| Resource | Link | Keterangan |
|---|---|---|
| Malware Traffic Analysis | https://malware-traffic-analysis.net | PCAP real malware traffic |
| PCAP Repository | https://github.com/automayt/ICS-pcap | Koleksi PCAP files |
| EVTX Attack Samples | https://github.com/sbousseaden/EVTX-ATTACK-SAMPLES | Windows Event Log attack samples |
| Boss of the SOC (BOTS) | https://github.com/splunk/botsv3 | Splunk CTF dataset |

---

## 📖 Buku & Referensi Gratis

| Judul | Link | Keterangan |
|---|---|---|
| The Practice of Network Security Monitoring | https://nostarch.com/nsm | Richard Bejtlich — klasik SOC |
| Blue Team Handbook | Amazon / PDF | Incident response quick reference |
| NIST SP 800-61 | https://nvlpubs.nist.gov | Panduan incident response resmi |
| SANS Reading Room | https://www.sans.org/white-papers | Ribuan whitepaper gratis |

---

## 🎥 YouTube Channel Rekomendasi

| Channel | Fokus |
|---|---|
| John Hammond | CTF, malware analysis, blue team |
| NetworkChuck | Networking, Linux, cybersecurity fundamental |
| Gerald Auger (SimplyCyber) | SOC analyst career, threat intel |
| David Bombal | Networking, Wireshark, security tools |
| 13Cubed | Digital forensics & incident response |
| SANS Institute | Advanced security topics |

---

## 💡 Tips Belajar Efektif

1. **Practice > Teori** — Setiap konsep yang dipelajari, langsung coba di lab
2. **Dokumentasikan** — Tulis writeup setiap challenge yang diselesaikan
3. **Home lab wajib** — Manfaatkan Proxmox dari bootcamp untuk deploy Wazuh + ELK
4. **PCAP setiap hari** — 30 menit Wireshark analisis PCAP dari malware-traffic-analysis.net
5. **Build in public** — Upload writeup ke GitHub, tunjukkan ke hiring manager
