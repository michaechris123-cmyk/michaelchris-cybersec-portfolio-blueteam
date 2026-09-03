# Phishing Analysis Fundamentals - Investigation Report

##  Executive Summary
This investigation documents my completion of the TryHackMe Phishing Analysis Fundamentals room. The lab focused on understanding email protocols, header analysis, and identifying phishing indicators through practical analysis.

**Key Outcome:** Successfully identified and decoded a malicious PDF attachment hidden using Base64 encoding.

##  Learning Objectives
- Understand SMTP, POP3, and IMAP email protocols
- Analyze email headers for phishing indicators
- Identify suspicious email characteristics
- Use tools like CyberChef and VirusTotal
- Decode Base64 encoded attachments
- Understand SPF, DKIM, and DMARC authentication

##  Tools Used
- TryHackMe AttackBox
- Thunderbird (Email Client)
- CyberChef (Decoding)
- VirusTotal (Hash reputation)
- ARIN WHOIS (IP Lookup)

##  Investigation Findings

### Task 1: Email Headers Analysis
- **Analyzed raw email headers** to identify:
  - Originating IP addresses
  - Mail transfer agents 
  - Authentication results (SPF, DKIM, DMARC)

**Key Headers Identified:**
| Header | Value |
|--------|-------|
| From | ADT Security Services <newsletters@ant.anki-tech.com> |
| To | alexa@yahoo.com |
| Reply-To | reply@ant.anki-tech.com |
| Date | 6/21/21, 15:35 |

### Task 2: Email Body Analysis
- **Identified suspicious elements:**
  - Spoofed sender address
  - Suspicious PDF attachment
  - Generic greeting 
  - Urgent language requesting action

### Task 3: Base64 Attachment Analysis
- **Attachment Found:** `zmqpalgh.pdf`
- **Encoding Used:** Base64
- **Decoded Content:** PDF file structure confirmed
- **PDF Header:** `%PDF-1.6`
- **PDF ID:** `<36C74F91D8307D4481492498DE25FCDB>`

**Decoding Process:**
1. Located Base64 string in email raw source
2. Copied encoded content
3. Pasted into CyberChef
4. Applied "From Base64" recipe
5. Confirmed PDF structure (`%PDF-1.6` header)

### Task 4: Email Authentication Analysis

**Authentication Server:** `atlas102.free.mail.gq1.yahoo.com`

| Check | Result | Details |
|-------|--------|---------|
| **SPF** |  PASS | `smtp.mailfrom=teckbe.com` |
| **DKIM** | PASS | `header.i=@teckbe.com`, selector `dk2048` |
| **DMARC** | PASS | `p=NONE` (monitoring only) |

**Conclusion:** The email passed all authentication checks, indicating it was legitimately sent from `teckbe.com` with no domain spoofing detected,but we still have to check base64 for a malicious pdf or attachment

### Task 5: Threat Analysis
- **Malicious Intent:** Credential harvesting via fake login page
- **Tactics:** Social engineering, attachment-based phishing
- **MITRE ATT&CK Mapping:** T1566.001 

##  Indicators of Compromise (IOCs)

**All IOCs have been defanged for safe sharing.**

| Type | Indicator (Defanged) | Status |
|------|---------------------|--------|
| **IP** | 103[.]234[.]236[.]83 | Malicious |
| **Email** | newsletters[@]ant[.]anki-tech[.]com | Suspicious |
| **Email** | reply[@]ant[.]anki-tech[.]com | Suspicious |
| **Attachment** | zmqpalgh[.]pdf | Malicious |
| **PDF ID** | <36C74F91D8307D4481492498DE25FCDB> | Malicious |

##  Key Takeaways
- Email headers contain critical forensic evidence
- Authentication results (SPF, DKIM, DMARC) help verify email legitimacy
- Base64 encoding is commonly used to hide malicious attachments
- Multiple analysis tools should be used for validation
- Always defang URLs and IPs in reports: `hxxp://` instead of `http://`

##  Screenshots

| Screenshot | Description |
|------------|-------------|
| [Raw Email Source](screenshots/1-raw-email-source.png) | Complete raw email headers |
| [Originating IP](screenshots/2-originating-ip.png) | X-Originating-IP identified |
| [Base64 in Source](screenshots/3-raw-message-source.png) | Base64 encoded attachment |
| [CyberChef Decoding](screenshots/4-cyberchef-decoding.png) | Base64 decoding process |
| [Decoded PDF](screenshots/5-decoded-pdf.png) | PDF structure confirmed |

##  References
- [TryHackMe Room](https://tryhackme.com/room/phishingemails1tryoe)
- [Email Header Analysis Guide](https://www.cisco.com/c/en/us/about/security-center/email-header-analysis.html)
- [MITRE ATT&CK: Spearphishing Attachment](https://attack.mitre.org/techniques/T1566/001/)

---
*Investigation Date: [2/9/2026]*  
*Investigator: Michael Chris*
*SOC Analyst Portfolio - Kenya 🇰🇪*
