# Task 15: Vulnerability Assessment

## 🚩 Project Overview
This task involved performing an automated Vulnerability Assessment (VA) using **Nessus Essentials**. The objective was to scan a target system, identify security weaknesses (such as missing patches or misconfigurations), and prioritize them based on their **CVSS** (Common Vulnerability Scoring System) scores.

## 🛠️ Tools Used
* **Nessus Essentials:** Industry-standard vulnerability scanner.
* **Target:** Ubuntu 22.04 LTS (Virtual Machine).

## 🔍 Methodology
1.  **Scope Definition:** Targeted the internal IP `192.168.1.50` (Linux VM) for a full port and vulnerability scan.
2.  **Configuration:** Configured a "Basic Network Scan" policy in Nessus to identify running services and known CVEs.
3.  **Scanning:** Executed the scan and monitored for real-time results.
4.  **Analysis:** Reviewed the findings, filtering out informational alerts to focus on actionable security risks.

## 📊 Key Findings
* **Total Vulnerabilities:** 3 (excluding Info)
* **Highest Risk:** **Medium (CVSS 6.4)** - SSL Certificate Trust Issues.
* **Observations:** The system is relatively secure due to the hardening performed in Task 14, but lacks a valid public SSL certificate and strict SMB signing.

## 🛡️ Remediation Strategy
1.  **SSL/TLS:** In a production environment, a valid certificate from a Trusted CA (like Verisign or Let's Encrypt) would be installed to resolve the encryption trust error.
2.  **SMB Hardening:** The `smb.conf` file will be updated to enforce message signing (`server signing = mandatory`) to prevent local Man-in-the-Middle attacks.

---
*Completed as part of the Elevate Labs Internship.*
