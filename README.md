# 🛡️ Automated Recon & Vulnerability Assessment Pipeline

A robust, multi-threaded Bash automation tool designed for security researchers, penetration testers, and SOC analysts to streamline attack surface reconnaissance and automated vulnerability scanning.

---

## 🚀 Features

- **Smart Target & Liveness Validation:** Automatically identifies whether the input is an IP address or a Domain, performing liveness checks via `ping`, `nc` (Netcat), and `nslookup` to avoid wasting time on dead hosts.
- **Comprehensive Reconnaissance:** Executes `whois` queries and performs deep `nmap` scans (`-sV`, `-sC`, `-O`, `-p-`) for service, version, and OS detection.
- **Automated Outdated Version Detection:** Parses Nmap output automatically to flag known vulnerable or outdated software versions (e.g., Apache, OpenSSH, vsftpd, MySQL).
- **Web Services Discovery & Vulnerability Scanning:** Detects running HTTP/HTTPS web services across common ports and automatically deploys **Nikto** to scan for critical/high web vulnerabilities and missing security headers.
- **Parallel Processing:** Leverages GNU `parallel` to run fast, multi-threaded reconnaissance across multiple targets simultaneously.
- **Structured Logging:** Automatically organizes results into target-specific directories, maintaining a clean `logs.txt` and a dedicated `vulnerabilities.txt` summary file.

---

## 🛠️ Prerequisites

Make sure the following tools are installed on your Kali Linux / Linux environment:
- `nmap`
- `nikto`
- `whois`
- `nc` (Netcat)
- `parallel` (GNU Parallel)

---

## 📦 Installation

Clone the repository and make the script executable:

```bash
git clone https://github.com/mohamed867/Bash_Projects.git
cd Bash_Projects
chmod +x recon.sh
```

---

## ⚙️ Usage

### 1. Scan a single target (Domain or IP):
```bash
./recon.sh example.com
```

### 2. Scan multiple targets from a file (Multi-threaded):
```bash
./recon.sh -f targets.txt
```

---

## 📂 Output Structure

The script automatically creates an `output/` directory structured as follows:

```text
output/
├── logs.txt              # Global execution logs with timestamps
├── vulnerabilities.txt   # Summary of detected vulnerabilities/outdated versions
└── <target-ip-or-domain>/
    ├── whois.txt         # WHOIS reconnaissance data
    ├── nmap.txt          # Nmap comprehensive scan results
    └── nikto.txt         # Nikto web vulnerability scan results
```

---

## 👤 Author

* **Mohamed Abdelgawad**
* **GitHub:** [mohamed867](https://github.com/mohamed867)
* **LinkedIn:** [Mohamed Abdelgawad](https://www.linkedin.com/in/mohamed-abdelgawad-5b5a64321/)
