# Threat Intelligence Reports Portfolio

![MITRE ATT&CK](https://img.shields.io/badge/MITRE-ATT%26CK-red)
![Python](https://img.shields.io/badge/Python-3.10-blue)
![Status](https://img.shields.io/badge/Status-Active-green)

# Threat Intelligence Reports Portfolio

A collection of threat intel write-ups, IOC collections, and MITRE ATT&CK mappings I put together while learning and doing hands-on analysis. Each report is written like a real-world intelligence product and includes:

- Executive summary  
- Threat actor background  
- Campaign analysis  
- MITRE ATT&CK mapping  
- Indicators of Compromise (IOCs)  
- Defensive recommendations

This project highlights my ability to:
- Collect & analyze OSINT for active campaigns
- Map attacker **TTPs -> to MITRE ATT&CK**
- Package IOCs so they can be dropped into SIEM/EDR
- Present fingings clearly for both analysts and non-technical stakeholders

---

## Quick links
- Kimsuky Deepfake Military ID Campaign — `./Kimsuky_Deepfake_MilitaryID/Report.md`

---

## Example IOC table

IOCs are stored as CSVs for easy ingestion. Typical fields: Type, Value, Description, First Seen, Source.

| Type         | Value                                  | Description      | First Seen  | Source          |
|--------------|----------------------------------------|------------------|-------------|-----------------|
| IPv4         | 183.111.174.34                         | C2 server        | 2025-09-15  | AlienVault OTX  |
| FileHash-MD5 | 09dabe5ab566e50ab4526504345af297       | Malware sample   | 2025-09-15  | AlienVault OTX  |
| Domain       | example-malicious.com                  | Malicious domain | 2025-09-15  | AlienVault OTX  |


---

## Tools / Techniques
- Suricata, Wireshark for PCAP/traffic analysis  
- Splunk (labs) for log parsing & detection testing
- Python & Bash scripting for enrichment/automation
- MITRE ATT&CK for TTP mapping and heatmap visualization

---

## About me
**Joseph Mastraccio** — entry-level cybersecurity practitioner focused on threat hunting and analysis.  
GitHub: https://github.com/Jwmastraccio | jwmastraccio@gmail.com

---

This project is for learning and portfolio use.
