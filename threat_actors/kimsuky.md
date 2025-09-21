# Kimsuky (aka Thallium / APT43)

**Quick summary**
Kimsuky is a DPRK-linked group that focuses on espionage and information theft. They tend to target government and defense organizations, especially in South Korea, but have broader activity as well.

**Common TTPs**
- Initial access: spear-phishing, malicious attachments, targeted social engineering (including fake identity documents)  
- Execution: obfuscated scripts, PowerShell-based payloads  
- Persistence: scheduled tasks, registry run keys  
- Evasion: obfuscation, file packing, DLL side-loading  
- C2: custom malware families and application-layer protocols

**Malware families often associated**
- BabyShark  
- ReconShark  
- KimsukyLoader

**Relevant ATT&CK techniques**
- T1566 — Phishing  
- T1027 — Obfuscation  
- T1059.001 — PowerShell  
- T1071 — Application layer protocol (C2)

**Recommended defenses**
- Log and alert on encoded PowerShell or long/obfuscated command lines.  
- Block or monitor suspicious domains and IPs from the IOC lists.  
- Use EDR features to catch persistence mechanisms (schedules, run keys).  
- Run suspicious attachments in a sandbox before allowing delivery to users.  
- Regular phishing awareness exercises, focused on identity-document lures.

**Notes on source and trust**
I collected IOCs from open sources (AlienVault OTX, other OSINT platforms) and cross-checked when possible. Treat them as starting points for investigation and validation in your environment.
