# Threat Intelligence Report
## Kimsuky Deepfake Military ID Campaign

---

### 1. Executive Summary
The Kimsuky APT, a North Korea-linked threat actor, conducted a sophisticated spear-phishing campaign leveraging AI-generated deepfake military identification documents. This campaign targeted South Korean defense and government personnel, aiming to compromise sensitive networks and exfiltrate strategic information.
Analysis of collected indicators and network traffic revealed that the actor used obfuscated malware delivered via phishing emails, followed by command-and-control (C2) communication and lateral movement attempts within affected networks. The attack demonstrated advanced evasion techniques, including the use of fake credentials and beaconing behaviors that mimic legitimate traffic.
This investigation identified key indicators of compromise (IOCs), including malicious domains, C2 IP addresses, and malware file hashes, which can be integrated into SIEM and endpoint detection tools to prevent or mitigate future intrusions. Recommended defensive measures include enhanced email filtering, endpoint monitoring for unusual parent/child process activity, and alerting on suspicious DNS or network traffic patterns.
---

### 2. Threat Actor Background
- **Name:** Kimsuky (a.k.a. Thallium, Velvet Chollima)
-  **Origin:** Suspected North Korea
-  **Motivations:** Espionage, intelligence collection on defense/government targets
-  **History:** Active since ~2012, frequently targeting South Korea, policy think tanks, and government agencies
Kimsuky is a North Korea-linked Advanced Persistent Threat (APT) group that has been active since at least 2012. The group primarily targets South Korean government agencies, think tanks, and defense contractors, but has also conducted campaigns against international organizations with interests in the Korean Peninsula. Their operations typically focus on intelligence collection, credential theft, and surveillance of strategic initiatives.
Tactics, Techniques, and Procedures (TTPs):
Spear-Phishing Campaigns: Use of personalized emails and malicious attachments to compromise targets.
Malware Deployment: Obfuscated malware, often in the form of backdoors or keyloggers, designed to evade traditional detection.
Command & Control (C2): Persistent communication with attacker-controlled servers for data exfiltration and remote access.
Credential & Identity Exploitation: Including the use of AI-generated deepfake documents, such as military IDs, to gain trust and access.
Kimsuky has consistently demonstrated high operational discipline, combining social engineering with technical evasion methods. Understanding their historical campaigns provides context for detecting similar activity, mapping MITRE ATT&CK techniques, and preparing defensive measures.
References / OSINT Sources:
MITRE ATT&CK: Kimsuky (https://attack.mitre.org/groups/G0094/)
CISA Advisory on Kimsuky (https://www.cisa.gov/uscert/ncas/alerts/AA20-0001)
AlienVault OTX Reports (https://otx.alienvault.com/)
---

### 3. Campaign Overview
- **Initial Access:** Spear-phishing emails mimicking South Korea military ID issuance
- **Malware Delivery:** Obfuscated batch + AutoIt loader
- **Execution:** PowerShell & Windows command shell
- **Command & Control:** Connections to known malicious IPs (see IOCs)
- **Innovation:** Use of AI/ChatGPT for realistic fake identity documents

Campaign Overview

The Kimsuky Deepfake Military ID campaign was designed to exploit human trust and gain unauthorized access to sensitive networks within South Korean defense and government organizations. The attack leveraged spear-phishing emails containing AI-generated deepfake military identification documents to convince targets to open attachments or click on links.
Observed Attack Flow:
Initial Compromise: Target receives a tailored phishing email with a deepfake ID attachment.
Malware Deployment: Opening the attachment triggers obfuscated malware that establishes persistence.
Command & Control (C2): Infected endpoints initiate communication with remote servers (C2 IPs documented in IOCs) to exfiltrate data and receive additional instructions.
Beaconing & Lateral Movement: The malware demonstrates beaconing behavior and abnormal parent/child process relationships, suggesting attempts to move laterally within the network.
Key Findings:
Multiple malicious domains and IP addresses were identified as part of the C2 infrastructure.
DNS traffic anomalies indicated data exfiltration attempts.
File hashes of deployed malware were documented for detection and mitigation.
Evidence of AI-generated deepfake IDs highlights advanced social engineering techniques.
Implications:
This campaign underscores the importance of layered security controls, including email filtering, endpoint monitoring, and anomaly detection. Analysts should prioritize monitoring for unusual process hierarchies, beaconing behaviors, and suspicious C2 traffic patterns.
Next Steps / Recommended Focus for Detection:
Deploy alerts for suspicious DNS requests and unexpected outbound connections.
Integrate identified IOCs into SIEM and endpoint detection platforms.
Conduct end-user training on identifying spear-phishing attempts, especially those leveraging fake identification documents.

---

### 4. MITRE ATT&CK Mapping

The Kimsuky campaign demonstrates multiple attacker techniques that align with the MITRE ATT&CK framework. Mapping these TTPs helps analysts understand the attack lifecycle and prioritize defensive actions.

| **Tactic**        | **Technique**                       | **Observed Behavior / Evidence**                                 | **MITRE ID** |
| ----------------- | ----------------------------------- | ---------------------------------------------------------------- | ------------ |
| Initial Access    | Spearphishing Attachment            | Target received emails with AI-generated deepfake ID attachments | T1566.001    |
| Execution         | PowerShell                          | Malicious scripts executed via PowerShell to deploy malware      | T1059.001    |
| Defense Evasion   | Obfuscated Files or Information     | Malware was obfuscated to avoid signature detection              | T1027        |
| Command & Control | Standard Application Layer Protocol | Infected hosts beaconed to C2 servers                            | T1071        |
| Credential Access | Input Capture                       | Keylogger activity observed                                      | T1056        |
| Exfiltration      | Exfiltration Over C2 Channel        | Data sent to remote IP addresses                                 | T1041        |



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
