# 🔐 Security Incident Analysis: Social Media Account Compromise

### Personal Case Study | February 2025

-----

## 📋 Incident Summary

|Field                      |Details                                                |
|---------------------------|-------------------------------------------------------|
|**Date of Incident**       |February 22–24, 2025                                   |
|**Platform Targeted**      |Snapchat (Web + Mobile)                                |
|**Attack Type**            |SMS-Based 2FA Bypass / Credential Attack               |
|**Attacker Location**      |Addis, LA, United States (IP: 102.129.234.51)          |
|**Device Used by Attacker**|iPhone 11 Pro Max                                      |
|**Account Owner Location** |Oklahoma City, OK                                      |
|**Outcome**                |Unauthorized access achieved briefly; account recovered|

-----

## 🕐 Timeline of Events

Feb 22, 2025 — Multiple SMS Codes Received

- Subject received 4+ unsolicited Snapchat login codes in rapid succession
- Codes received: 939370 / 873756 / 092151 / 062096
- Subject was asleep and did not authorize any of these attempts
- Snapchat locked the account temporarily due to suspicious activity

Feb 24, 2025 — 12:15 AM

- Snapchat sent a “Was this you?” verification notification
- Login attempted from Mobile Safari for iOS near Oklahoma City, OK
- Subject did not approve this request

Feb 24, 2025 — 12:23 AM

- Snapchat confirmed unauthorized login from iPhone 11 Pro Max
- Login location: Addis, LA (IP: 102.129.234.51)
- Account was accessed without the subject’s knowledge or approval

-----

## 🔍 Attack Vector Analysis

### What Happened — Step by Step
[Attacker] → Enters victim username/password on Snapchat Web
           → Snapchat sends SMS verification code to victim's phone
           → Multiple attempts made (4+ codes sent = 4+ login attempts)
           → On one attempt, attacker successfully obtained the SMS code
           → Attacker enters code → Account compromised
           → Snapchat detects anomaly (different location/device) → Sends alert

### Possible Attack Methods Investigated

1. SS7 Protocol Exploitation (Most Likely)

- SS7 (Signaling System No. 7) is the global telecom protocol used to route calls and SMS
- Known vulnerability: attackers with SS7 network access can silently intercept SMS messages
- The victim’s SIM card continued working normally — consistent with SS7 (not SIM swap)
- SMS codes arrived at the attacker before reaching the victim’s phone

2. SIM Swapping (Ruled Out)

- SIM swap requires contacting the carrier to transfer the phone number
- If successful, the victim’s SIM would stop working
- Victim’s SIM remained functional throughout — this method was ruled out

3. Social Engineering

- Attacker may have had prior knowledge of the victim (account username, email)
- Used this to initiate password reset and intercept SMS via SS7

-----

## 🛡️ Why SMS 2FA Failed Here

SMS-based two-factor authentication has a known weakness: it relies on the security of the telephone network (SS7), which was designed in the 1970s without authentication mechanisms.

> “SMS OTPs are vulnerable to real-time phishing, SS7 attacks, and SIM swapping. They are better than no 2FA, but should not be considered strong authentication.” — NIST SP 800-63B

The attacker did not need the victim’s physical phone. They only needed to intercept the SMS — which SS7 vulnerabilities make possible.

-----

## 📊 Key Observations

- Multiple rapid login attempts suggest an automated or script-assisted attack
- Different login location (Addis, LA vs Oklahoma City, OK) confirms unauthorized access
- Snapchat’s anomaly detection worked — it flagged the suspicious login and notified the victim
- Account lockout triggered after repeated failed attempts — a defense mechanism that slowed the attack

-----

## ✅ Incident Response Actions Taken

1. Immediately changed account password upon receiving alert
1. Reviewed all active login sessions and terminated unknown devices
1.
