SOC Incident Report Tool
A Security Operations Center (SOC) tool for reviewing security alerts and documenting incident reports.

What It Does
When a suspicious activity is detected in your environment, this tool helps you:

Review the alert details (process name, host, timestamp, etc.)
Classify the incident as True Positive or False Positive
Write a case report with findings and recommended actions
Decide whether to escalate the alert


Example Alert
This is what a real alert looks like inside the tool:


Event ID 1026 — Suspicious Parent-Child Relationship
FieldValueHostwin-3450Processnslookup.exeParent Processpowershell.exeSeverityHighDetectedFeb 4th 2026 at 12:29
In this case, powershell.exe launched nslookup.exe from a folder called exfiltration and sent encoded data to an external domain — a strong sign of DNS-based data exfiltration.

Incident Report Fields
FieldDescriptionIncident classificationTrue Positive or False PositiveCase reportYour written analysis of what happenedEscalationWhether the alert needs to go to L2
