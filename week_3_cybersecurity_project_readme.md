# 🛡️ Week 3 Project: Security Assessments & Password Cracking Labs

Welcome to my repository for **Week 3** of the **Networkwalks Academy** Cybersecurity training program. This repository documents my hands-on security assessments, hash extraction workflows, password-cracking methodologies, and environment automation using Kali Linux, John the Ripper, and the HexStrike AI MCP server.

---

## 📋 Project Overview & Objectives

* **Program:** Networkwalks Cybersecurity Training (Week 3)
* **Focus Areas:** Penetration testing workflows, cryptographic hash auditing, dictionary-based password attacks, and security tool automation.
* **Environment:** Kali Linux Virtual Machine integrated with HexStrike AI MCP backend server.
* **Core Deliverables:**
  * Configuring and troubleshooting an AI-assisted offensive security MCP server environment.
  * Isolating and extracting cryptographic hashes from password-protected PDF files.
  * Executing wordlist-based password recovery using John the Ripper (`john`).
  * Capturing and verifying all required assessment flags.

---

## 🛠️ Tools & Technologies Used

* **Operating System:** Kali Linux
* **Password Auditing:** John the Ripper (`john`), `pdf2john`
* **Wordlists:** `rockyou.txt`
* **Automation & Reconnaissance:** HexStrike AI MCP Server (`v6.0.0`), Python Virtual Environments, `nmap`, `subfinder`, `katana`, `dalfox`, `ghidra`, `gdb`

---

## ⚙️ Methodology & Execution Walkthrough

### 1. Environment & Tooling Setup
To streamline reconnaissance and security assessments, the HexStrike AI MCP backend server was configured on Kali Linux alongside essential penetration testing binaries (`subfinder`, `katana`, `dalfox`, `arjun`, `rustscan`, `gdb`, and `ghidra`).

### 2. Extracting Cryptographic Hashes from Protected PDFs
To analyze protected target documents (`hash3.networkwalks_flag1.pdf`), the `pdf2john` utility was used to isolate the document's encryption hash into a readable format:
```bash
cd ~/Desktop
pdf2john hash3.networkwalks_flag1.pdf > pdf_hash.txt
```

### 3. Preparing Wordlists & Cracking the Password
After extracting the standard Kali Linux `rockyou.txt` dictionary archive, John the Ripper was executed against the extracted PDF hash to recover the cleartext password:
```bash
# Uncompress the wordlist
sudo gzip -d /usr/share/wordlists/rockyou.txt.gz

# Run dictionary attack against the PDF hash
john --wordlist=/usr/share/wordlists/rockyou.txt pdf_hash.txt
```

---

## 🚩 Captured Flags Summary

All target flags for the Week 3 modules were successfully captured, decrypted, and verified:

| Lab Module | Flag Identifier | Status |
| :--- | :--- | :--- |
| **General Security Lab** | `nw{cybersecurity_flag_captured_2608}` | ✅ Captured |
| **Network Security Assessment** | `nw{networkwalks_flag_260821_1}` | ✅ Captured |
| **PDF Password Cracking (JTR)** | `nw{networkwalks_flag1_jtr_270521_1}` | ✅ Captured |
| **Advanced Persistence Lab** | `nw{networkwalks_persistence_jtr_270521}` | ✅ Captured |

---

## 📸 Proof of Completion

> *Note: Upload your 4 completion certificate screenshots into an `images/` folder in your repository to display them cleanly here.*

* `Screenshot 1` — General Security Flag Captured (`nw{cybersecurity_flag_captured_2608}`)
* `Screenshot 2` — Network Security Flag Captured (`nw{networkwalks_flag_260821_1}`)
* `Screenshot 3` — John the Ripper PDF Flag Captured (`nw{networkwalks_flag1_jtr_270521_1}`)
* `Screenshot 4` — Persistence & Wordlist Flag Captured (`nw{networkwalks_persistence_jtr_270521}`)

---

## 📈 Key Takeaways

* **Persistence & Wordlist Selection:** Effective password auditing relies heavily on selecting the appropriate wordlist and understanding hash formats.
* **Environment Management:** Properly managing Python virtual environments, system dependencies, and tool paths is critical when deploying automated security frameworks.

---

*Completed as part of the **Networkwalks Academy** Cybersecurity curriculum.*