# Threat Intelligence Report
## Kimsuky Deepfake Military ID Campaign

---

### 1. Executive Summary
The North Korea-aligned **Kimsuky APT** group has launched a spear-phishing campaign targeting South Korea defense institutions. The campaign leverages **AI-generated deepfake military ID cards** to add credibility, delivered via spear-phishing emails. Malware was executed using obfuscated batch files and AutoIt scripts, with persistence achieved through scheduled tasks. This campaign highlights the evolving use of **AI in state-sponsered cyber espionage**.

---

### 2. Threat Actor Background
- **Name:** Kimsuky (a.k.a. Thallium, Velvet Chollima)
-  **Origin:** Suspected North Korea
-  **Motivations:** Espionage, intelligence collection on defense/government targets
-  **History:** Active since ~2012, frequently targeting South Korea, policy think tanks, and government agencies

---

### 3. Campaign Overview
- **Initial Access:** Spear-phishing emails mimicking South Korea military ID issuance
- **Malware Delivery:** Obfuscated batch + AutoIt loader
- **Execution:** PowerShell & Windows command shell
- **Command & Control:** Connections to known malicious IPs (see IOCs)
- **Innovation:** Use of AI/ChatGPT for realistic fake identity documents

---

### 4. MITRE ATT&CK Mapping
| Technique ID | Name                                 | Observed Use |
| T1566        | Phishing                             | Spear-phishing emails with fake ID lure |
| T1059.001    | PowerShell                           | Executing malicious scripts |
| T1027        | Obfuscated Files or Information      | Batch/AutoIt obfuscation |
| T1036        | Masquerading                         | Fake ID cards & processes |
| T1053.005    | Scheduled Task                       | Persistence Mechanism |

---

### 5. Indicators of Compromise (IOCs)
| Type            | Value                                     | Source |
| IPv4            | 183.111.174.34                            | AlienVault OTX |
| IPv4            | 121.254.129.86                            | AlienVault OTX |
| Domain          | Example[.]com (replace w/ real)           | AlienVault OTX |
| FileHash-MD5 | 09dabe5ab566e50ab4526504345af297             | AlienVault OTX |

*Full list in ['IOCs.csv'](./IOCs.csv)*

---

### 6. Defensive Recommendations
1. Train employees on phisiong detection, focusing on **fake ID verification attempts**.
2. Monitor endpoint logs for **AutoIt and PowerShell execution anomalies**.
3. Block and monitor listed **malicious IPs/domains**.
4. Deploy EDR rules for suspicious parent/child process chains (e.g., 'winword.exe' -> 'powershell.exe').
5. subscribe to updated threat intel feeds (AlienVault, CrowdStrike, Mandiant).

---

### 7. References
-AlienVault OTX Pulse : [AI-Driven Deepfake Military ID Fraud Campaign](https://otx.alienvault.com)
-MITRE ATT&CK Group G0094: [Kimsuky](https://attack.mitre.org/groups/G0094/)
