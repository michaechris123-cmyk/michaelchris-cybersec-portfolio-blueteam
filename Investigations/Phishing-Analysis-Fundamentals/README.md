### Phishing Analysis Fundamentals - Investigation Report

 Executive Summary
This investigation documents my completion of the TryHackMe Phishing Analysis Fundamentals room. The lab focused on understanding email protocols, header analysis, and identifying phishing indicators.

 Learning Objectives
- Understand SMTP, POP3, and IMAP email protocols
- Analyze email headers for phishing indicators
- Identify suspicious email characteristics
- Use tools like CyberChef and VirusTotal

 ### Tools Used
- TryHackMe AttackBox
- CyberChef
- VirusTotal
- Email header analysis tools

### Investigation Findings

### Task 1: Email Headers Analysis
- Analyzed raw email headers to identify:
  - Originating IP addresses
  - Mail transfer agents 
  - Authentication results

### Task 2: Email Body Analysis
- Identified suspicious elements in email body:
  - Spoofed sender addresses
  - Malicious links
  - Social engineering tactics

### Task 3: Email Analysis Tools
- Used CyberChef to decode obfuscated content
- Used VirusTotal to check suspicious attachments

##  Key Takeaways
- Email headers contain critical forensic evidence
- Authentication results (SPF, DKIM, DMARC) help verify email legitimacy
- Multiple analysis tools should be used for validation

## 📚 References
- [TryHackMe Room](https://tryhackme.com/room/phishingemails1tryoe)
- [Email Header Analysis Guide](https://www.cisco.com/c/en/us/about/security-center/email-header-analysis.html)

***
*Investigation Date: [9/2/2026]*  
*Investigator: chris michael ochieng*
