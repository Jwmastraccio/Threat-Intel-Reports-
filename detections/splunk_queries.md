# Splunk detection examples

A few simple queries you can drop into Splunk (or use as starting points). Tweak fields/indexes to match your environment.

## Suspicious PowerShell (encoded / long commandline)
```spl
index=windows sourcetype="WinEventLog:Security" EventCode=4688
New_Process_Name="*powershell.exe"
| where like(CommandLine, "%-EncodedCommand%") OR like(CommandLine, "%Base64%")
| stats count by Account_Name, New_Process_Name, CommandLine

# DNS queries for known bad hostnames

index=dns sourcetype="dns:query"
query="*.example-malicious.com"
| stats count by src_ip, query

# Email attachment matching an IOC hash

index=email sourcetype="exchange"
attachment_hash="09dabe5ab566e50ab4526504345af297"
| table _time, sender, recipient, subject, attachment_name


---

# 4) `detections/suricata.rules` (unchanged format, concise comments)

```rules
# Basic Suricata rules for sample IOCs
# Update SIDs if you integrate into a ruleset

alert dns any any -> any any (msg:"Kimsuky - known malicious domain"; dns.query; content:"example-malicious.com"; nocase; sid:100001;)
alert ip any any -> 183.111.174.34 any (msg:"Kimsuky - known C2 IP"; sid:100002;)
alert tcp any any -> any 445 (msg:"Possible SMB lateral movement - check context"; flow:to_server,established; sid:100003;)
