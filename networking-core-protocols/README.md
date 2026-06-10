# Networking Core Protocols

## Task 1: Introduction

### Description

We will cover the following protocols:
- WHOIS
- DNS
- HTTP and FTP
- SMTP, POP3, and IMAP

## Task 2: DNS:Remembering Addresses

### Description

- Domain Name System (DNS) is responsible for properly mapping a domain name to an IP address.
- DNS operates at Layer 7 (Application Layer) of ISO OSI model.
- DNS traffic uses UDP port 53 by default and TCP port 53 as a default fallback.
- There are many types of DNS records such as A(maps a hostname to one or more IPv4 addresses), AAAA(maps a hostname to one or more IPv6 addresses), CName(maps a domain name to another domain name) and MX( mail     server responsible for handling emails for a domain).

#### Question

Which DNS record type refers to IPv6?

#### Answer

AAAA

#### Question

Which DNS record type refers to the email server?

#### Answer

MX

## Task 3: WHOIS


### Description

- WHOIS record provides information about the entity that registered a domain name, including name, phone number, email, and address.
- We can also use one of the privacy services that hide all information from the WHOIS records.

#### Question

When was the x.com record created? Provide the answer in YYYY-MM-DD format.

#### Answer

![Task 3.0](images/ncp-t3-0.png)

1993-04-02

#### Question

When was the twitter.com record created? Provide the answer in YYYY-MM-DD format.

#### Answer

![Task 3.1](images/ncp-t3-1.png)

2000-01-21

## Task 4: HTTP(S) : Accessing the Web


### Description

- HTTP and HTTPS commonly use TCP ports 80 and 443, respectively, and less commonly other ports such as 8080 and 8443.
- Some of the commands or methods that your web browser commonly issues to the web server are: GET, POST, PUT and DELETE.

#### Question

Use telnet to access the file flag.html on 10.48.188.67. What is the hidden flag?

#### Answer

![Task 4.0](images/ncp-t4-0.png)
![Task 4.1](images/ncp-t4-1.png)

THM{TELNET-HTTP}

## Task 5: FTP: Transferring Files


### Description

- FTP(File Transfer Protocol), is efficient for file transfer and when all conditions are equal, it can achieve higher speeds than HTTP.
- FTP server listens on TCP port 21 by default.
- Some commands defined by the FTP protocol are: USER, PASS, RETR, STOR.



#### Question

Using the FTP client ftp on the AttackBox, access the FTP server at 10.48.188.67 and retrieve flag.txt. What is the flag found?

#### Answer

![Task 5.0](images/ncp-t5-0.png)

THM{FAST-FTP}

## Task 6: SMTP: Sending Email


### Description

- The SMTP server listens on TCP port 25 by default.
- Simple Mail Transfer Protocol (SMTP) use comands such as HELO/EHLO, MAIL FROM, RCPT TO, DATA, . .

#### Question

Which SMTP command indicates that the client will start the contents of the email message?

#### Answer

DATA

#### Question

What does the email client send to indicate that the email message has been fully entered?

#### Answer

.

## Task 7: POP3: Receiving Email


### Description

- An email client sends its messages by relying on SMTP and retrieves them using POP3.
- The POP3 server listens on TCP port 110 by default.

#### Question

Looking at the traffic exchange, what is the name of the POP3 server running on the remote server?

#### Answer

![Task 7.0](images/ncp-tp7-0.png)

Dovecot

#### Question

Use telnet to connect to 10.48.172.46’s POP3 server. What is the flag contained in the fourth message?

#### Answer

![Task 7.1](images/ncp-t7-1.png)

THM{TELNET_RETR_EMAIL}

## Task 8: IMAP: Synchronizing Email


### Description

- Internet Message Access Protocol allows synchronizing read, moved, and deleted messages.
- IMAP server listens on TCP port 143 by default.

#### Question

What IMAP command retrieves the fourth email message?

#### Answer

FETCH 4 body[]










