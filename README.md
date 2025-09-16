# Threat Intelligence Reports Portfolio

This repository contains a portfolio of **threat intelligence reports** created as part of my cybersecurity work and study. Each report is structured like a professional intelligence product and includes:

- **Executive Summary**  
- **Threat Actor Background**  
- **Campaign Analysis**  
- **MITRE ATT&CK Mapping**  
- **Indicators of Compromise (IOCs)**  
- **Defensive Recommendations**  

The reports demonstrate my ability to:  

- Analyze cyber threat campaigns using open-source intelligence (OSINT)  
- Map attacker TTPs to **MITRE ATT&CK**  
- Document and organize IOCs in a format suitable for SIEM/EDR ingestion  
- Communicate findings in both technical and non-technical language  

---

## Reports

### [Kimsuky Deepfake Military ID Campaign](./Kimsuky_Deepfake_MilitaryID/Report.md)  
- **Adversary:** Kimsuky (North Korea-linked APT)  
- **Tactics:** AI-generated deepfake IDs, spear-phishing, obfuscated malware  
- **Targeted Industry:** South Korean defense and government  
- **Key MITRE ATT&CK IDs:**  
  - T1566 – Phishing  
  - T1027 – Obfuscation  
  - T1059.001 – PowerShell  

---

## IOC Data

Indicators of Compromise (IOCs) for each campaign are available in **CSV format** for easy ingestion into SIEM/EDR tools.  
**Fields include:** Type, Value, Description, First Seen, Source  

**Example:**

| Type          | Value                       | Description      | First Seen  | Source          |
|---------------|----------------------------|----------------|------------|----------------|
| IPv4          | 183.111.174.34             | C2 server       | 2025-09-15 | AlienVault OTX |
| FileHash-MD5  | 09dabe5ab566e50ab4526504345af297 | Malware sample | 2025-09-15 | AlienVault OTX |
| Domain        | example-malicious.com       | Malicious domain| 2025-09-15 | AlienVault OTX |

---

## Tools & Technologies Demonstrated

- **Network Analysis:** Suricata, Wireshark, PCAP analysis  
- **SIEM / Log Analysis:** Splunk (labs), log parsing  
- **Scripting / Automation:** Python, Bash  
- **Threat Modeling:** MITRE ATT&CK mapping  

---

## Author

**Joseph Mastraccio**  
Entry-Level Cybersecurity Professional | [GitHub](https://github.com/Jwmastraccio)  
Email: jwmastraccio@gmail.com  

---

*This portfolio is intended for educational and professional demonstration purposes.*
