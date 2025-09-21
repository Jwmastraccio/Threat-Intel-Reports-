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

This repo shows how I:
- Pull OSINT to analyze campaigns
- Map attacker TTPs to MITRE ATT&CK
- Package IOCs so they can be dropped into a SIEM/EDR
- Explain technical findings in plain English for stakeholders

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

## What’s in this repo

---

*This portfolio is intended for educational and professional demonstration purposes.*
