# Screenshots - Phishing Analysis Fundamentals

This folder contains screenshots from my Phishing Analysis Fundamentals investigation.

##  Investigation Screenshots

| Screenshot | Description |
|------------|-------------|
| [1-raw-email-source.png](1-raw-email-source.png) | Complete raw email headers |
| [use-message-source-to-view.png](use-message-source-to-view.png) |  use message souce to view the full raw message |
| [2-originating-ip.png](2-originating-ip.png) | X-Originating-IP identified |
| [3-raw-message-source.png](3-raw-message-source.png) | Full raw message source |
| [we-use-from-base-64-to-encode.png](we-use-from-base-64-to-encode.png) | because its a base64 we will select from base64 |
| [4-cyberchef-decoding.png](4-cyberchef-decoding.png) | CyberChef Base64 decoding |
| [5-decoded-pdf.png](5-decoded-pdf.png) | PDF structure confirmed |
| [6-authentication-results.png](6-authentication-results.png) | SPF/DKIM/DMARC results |
| [7-defanged-iocs.png](7-defanged-ip.png) | Defanged IOCs in report |

##  Tools Used
- TryHackMe AttackBox
- Thunderbird (Email Client)
- CyberChef (Decoding)

##  Analysis Summary
- **Email Type:** Phishing (credential harvesting)
- **Attachment Found:** `zmqpalgh.pdf` (Base64 encoded)
- **PDF Header:** `%PDF-1.6`
- **PDF ID:** `<36C74F91D8307D4481492498DE25FCDB>`
- **Authentication:** SPF=pass, DKIM=pass, DMARC=pass **(lab 3)**

---
*Screenshots from TryHackMe Phishing Analysis Fundamentals lab*
*Investigator: Michael Chris*
