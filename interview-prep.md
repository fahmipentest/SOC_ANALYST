# 🎤 Interview Prep — SOC Analyst

Kumpulan pertanyaan yang paling sering muncul saat interview SOC Analyst, lengkap dengan panduan jawaban.

---

## ❓ Pertanyaan Teknikal

### Networking
**Q: Jelaskan OSI Model dan berikan contoh serangan di setiap layer.**
> Layer 1 (Physical): cable tapping. Layer 2 (Data Link): ARP spoofing, MAC flooding. Layer 3 (Network): IP spoofing, ICMP flood. Layer 4 (Transport): SYN flood, port scanning. Layer 7 (Application): SQLi, XSS, phishing.

**Q: Apa perbedaan IDS dan IPS?**
> IDS (Intrusion Detection System) hanya mendeteksi dan memberikan alert. IPS (Intrusion Prevention System) mendeteksi DAN memblokir traffic secara aktif. IDS bersifat passive, IPS bersifat inline/active.

**Q: Jelaskan TCP 3-way handshake. Bagaimana attacker bisa mengeksploitasinya?**
> SYN → SYN-ACK → ACK. Attacker bisa melakukan SYN flood (DoS) dengan mengirim ribuan SYN tanpa menyelesaikan handshake, menghabiskan resource server (half-open connections).

---

### Windows & Active Directory
**Q: Event ID apa yang kamu monitor untuk deteksi brute force login?**
> Event ID **4625** (Failed Logon) — monitor volume tinggi dari satu sumber IP dalam waktu singkat. Juga Event ID **4624** (Successful Logon) setelah banyak failure untuk deteksi successful brute force.

**Q: Bagaimana cara mendeteksi Pass-the-Hash attack?**
> Monitor Event ID **4624** dengan Logon Type **3** (Network) dan Authentication Package **NTLM** (bukan Kerberos) dari akun privileged. Juga monitor penggunaan admin share (C$, ADMIN$) yang tidak biasa.

**Q: Apa itu Kerberoasting dan bagaimana cara mendeteksinya?**
> Attacker request Kerberos TGS ticket untuk service account, lalu crack offline. Deteksi: monitor Event ID **4769** (Kerberos Service Ticket Request) dengan Encryption Type **0x17** (RC4) dalam volume tinggi dari satu user.

---

### SIEM & Log Analysis
**Q: Bagaimana kamu melakukan triage terhadap sebuah alert?**
> 1. Baca detail alert (source IP, destination, timestamp, rule yang trigger). 2. Enrich IOC (lookup di VirusTotal, AbuseIPDB). 3. Cek konteks (apakah IP ini internal/external? User siapa?). 4. Pivot ke log lain (apakah ada aktivitas lain dari source yang sama?). 5. Klasifikasikan: True Positive / False Positive / Benign True Positive. 6. Dokumentasikan dan escalate jika perlu.

**Q: Apa itu false positive dan bagaimana kamu menanganinya?**
> False positive adalah alert yang trigger tapi bukan serangan nyata. Tangani dengan: verifikasi konteks bisnis, whitelist jika aktivitas legitimate, fine-tune rule untuk reduce noise. Jangan asal dismiss tanpa investigasi.

**Q: Splunk query apa yang kamu gunakan untuk deteksi brute force?**
> ```spl
> index=windows EventCode=4625
> | stats count by src_ip, user
> | where count > 10
> | sort -count
> ```

---

### Threat Intelligence
**Q: Jelaskan MITRE ATT&CK Framework.**
> MITRE ATT&CK adalah knowledge base teknik dan taktik yang digunakan attacker berdasarkan observasi dunia nyata. Terdiri dari 14 tactic (kolom) dan ratusan technique (baris). Digunakan untuk: mapping deteksi, gap analysis, threat intel sharing, dan komunikasi dengan tim.

**Q: Apa itu Cyber Kill Chain?**
> Model 7 tahap dari Lockheed Martin yang menggambarkan tahap serangan: Reconnaissance → Weaponization → Delivery → Exploitation → Installation → Command & Control → Actions on Objectives. SOC menggunakannya untuk identifikasi di tahap mana serangan bisa dihentikan.

**Q: Apa perbedaan IOC dan TTP?**
> IOC (Indicators of Compromise) adalah artefak forensik seperti IP, domain, hash — mudah diubah attacker. TTP (Tactics, Techniques, Procedures) adalah cara kerja attacker — jauh lebih sulit diubah karena berkaitan dengan behavior. TTP lebih valuable untuk deteksi jangka panjang (lihat Pyramid of Pain).

---

## ❓ Pertanyaan Scenario-Based

**Q: Kamu menerima alert SQL Injection dari WAF. Apa langkah investigasimu?**
> 1. Identifikasi source IP, target URL, payload yang digunakan. 2. Cek web server log — apakah ada request serupa sebelumnya? 3. Lookup source IP di AbuseIPDB/VirusTotal. 4. Cek apakah request berhasil (HTTP response code — 200 berarti berhasil). 5. Jika sukses: eskalasi segera, preserve log, isolasi jika perlu. 6. Jika blocked: dokumentasikan, fine-tune rule, monitor untuk follow-up.

**Q: User melaporkan komputernya lambat dan ada file aneh. Apa yang kamu lakukan?**
> 1. Isolasi endpoint dari jaringan (jangan matikan — preserve memory). 2. Ambil memory dump untuk analisis. 3. Jalankan Process Explorer — cari proses dengan nama aneh, parent process tidak wajar, atau network connection mencurigakan. 4. Cek Autoruns untuk persistence. 5. Upload file mencurigakan ke Any.run/VirusTotal. 6. Cek log SIEM untuk lateral movement dari endpoint tersebut. 7. Dokumentasikan timeline dan buat incident report.

**Q: Kamu menemukan traffic keluar ke IP asing secara berkala setiap 5 menit. Apa ini?**
> Pola beacon traffic — kemungkinan besar C2 (Command & Control) communication dari malware. Investigasi: lookup IP (Shodan, VirusTotal), analisis packet (Wireshark), identifikasi proses yang membuat koneksi, cek apakah ada data exfiltration, isolasi endpoint, dan eskalasi.

---

## ❓ Pertanyaan Behavioral

**Q: Ceritakan tentang pengalamanmu di cybersecurity.**
> *Gunakan STAR method: Situation, Task, Action, Result. Highlight offensive background sebagai keunggulan dalam memahami attacker mindset.*

**Q: Kenapa kamu ingin bekerja di SOC padahal background kamu offensive?**
> Offensive background justru menjadi keunggulan di SOC — saya memahami cara attacker berpikir, teknik yang mereka gunakan, dan bagaimana mereka menghindari deteksi. Ini membantu saya melakukan triage lebih akurat dan hunting lebih proaktif.

**Q: Bagaimana kamu tetap update dengan threat landscape terbaru?**
> Ikuti: SANS Internet Storm Center (daily diary), Krebs on Security, The Hacker News, Twitter/X security researchers, AlienVault OTX feeds, dan MITRE ATT&CK updates.

---

*Good luck dengan interviewnya! 💪*
