🛡️ Phishing Email Analysis Report

Platform: TryHackMe
Case: Phishing Case 01
Analyst: Alina
Role Target: SOC Analyst

1. Executive Summary

The objective of this lab was to analyze a suspicious email and determine whether it represents a phishing attempt. During the investigation, email headers, sender information, IP addresses, authentication records (SPF/DMARC), and the attached file were analyzed using industry-standard tools.

Based on the findings, the email exhibits multiple indicators of phishing activity, including suspicious sender information, abnormal email authentication results, and a malicious file attachment confirmed by VirusTotal.


2. Incident Description

A suspicious email was provided for analysis as part of a TryHackMe phishing investigation lab. The task required identifying key attributes of the email, verifying its authenticity, and assessing the potential threat posed by the attached file.

The investigation focused on:

Email header analysis

Source IP attribution

SPF and DMARC record verification

File hash generation and malware analysis

<img width="869" height="528" alt="image" src="https://github.com/user-attachments/assets/f4809813-d1e8-46c6-94f5-0dfe42c2d533" />
<img width="885" height="693" alt="image" src="https://github.com/user-attachments/assets/0cbfd1b4-1e3a-4422-be9e-fd43362d47c0" />

3. Tools and Environment

The following tools and platforms were used during the investigation:

Thunderbird – email header and content analysis

Linux Terminal – file hash generation

WHOIS – IP ownership lookup

MXToolbox – SPF and DMARC record analysis

VirusTotal – malware and reputation analysis


4. Email Header Analysis

The email was opened on the virtual machine using Thunderbird.
From the email headers and body, the following information was extracted:

Transfer Reference Number

Sender email address

Reply-To email address

Originating IP address

This information was used to assess whether the email originated from a legitimate source or was spoofed.

<img width="962" height="796" alt="image" src="https://github.com/user-attachments/assets/f2005d60-d527-4004-8ebc-311bbb2eabf5" />

<img width="969" height="866" alt="image" src="https://github.com/user-attachments/assets/438585dc-b29a-4985-8e3f-43442fb1f556" />

5. IP Address Attribution

The originating IP address identified in the email header was submitted to whois.com for further investigation.

The WHOIS lookup revealed ownership and registration details of the IP address. The results indicated that the IP address belongs to a hosting provider rather than a legitimate corporate mail server, which is commonly associated with phishing or spam campaigns.


<img width="992" height="818" alt="image" src="https://github.com/user-attachments/assets/2f0537f9-351d-4225-858e-298e1b12ede0" />

Conclusion:
The IP origin increases the likelihood that the email is malicious.

6. SPF and DMARC Analysis

To evaluate email authentication mechanisms, the Return-Path domain was analyzed using MXToolbox.

<img width="858" height="249" alt="image" src="https://github.com/user-attachments/assets/2c431afe-02f2-4aab-a1d7-560b9f105a47" />

The following records were checked:

SPF (Sender Policy Framework)

DMARC (Domain-based Message Authentication, Reporting & Conformance)

The results showed misconfigured or weak authentication records, allowing email spoofing.

Conclusion:
The absence or misconfiguration of SPF/DMARC records is a strong indicator of phishing activity.

7. Attachment Analysis

The email contained an attachment, which was saved locally for analysis.

<img width="865" height="521" alt="image" src="https://github.com/user-attachments/assets/ec81604f-89a5-4594-b8e6-c3878129eb23" />

7.1 Hash Generation

Using the terminal, a cryptographic hash of the file was generated to uniquely identify the attachment.

<img width="942" height="76" alt="image" src="https://github.com/user-attachments/assets/9b5d928b-05d9-4cdb-85d7-4ec9392e544c" />



7.2 VirusTotal Analysis

The generated hash was submitted to VirusTotal, where the file was analyzed by multiple antivirus engines.

VirusTotal results confirmed that the file is malicious, with detections reported by several security vendors.
<img width="1774" height="764" alt="image" src="https://github.com/user-attachments/assets/039a8ce5-e053-44f5-8455-1f045c971330" />

Conclusion:
The attachment poses a direct security risk and confirms the malicious intent of the email.

8. Indicators of Compromise (IOCs)

The following IOCs were identified during the investigation:

Sender email address info@mutawamarine.com

Reply-To email address info.mutawamarine@mail.com

Originating IP address 192.119.71.157

Return-Path domain mutawamarine.com

Malicious file hash  2e91c533615a9bb8929ac4bb76707b2444597ce063d84a4b33525e25074fff3f

These IOCs could be used to enhance detection and prevention mechanisms in a SOC environment.

9. Final Verdict

Based on the analysis of email headers, IP attribution, authentication records, and attachment behavior, this email is confirmed to be a phishing email with a malicious payload.

10. Recommended Response Actions

In a real SOC environment, the following actions are recommended:

Block the sender IP and associated domains

Add the file hash to endpoint protection blocklists

Update email filtering rules

Notify users about the phishing campaign

Monitor for additional emails using the same IOCs

11. Key Takeaways

This lab demonstrates the complete phishing analysis workflow used by SOC analysts, including:

Email header investigation

Threat intelligence enrichment

Authentication record verification

Malware analysis using hashes

IOC identification and incident response thinking

📌 This report was created as part of hands-on SOC training on the TryHackMe platform and reflects real-world phishing investigation techniques.
















