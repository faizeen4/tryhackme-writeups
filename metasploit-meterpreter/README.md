# Metasploit: Meterpreter

## Task 01: Introduction to Meterpreter

### Description

- Meterpreter is a Metasploit payload that supports the penetration testing process with many valuable components.
- Meterpreter has many versions which will provide different functionalities based on the target system.
- Meterpreter also aims to avoid being detected by network-based IPS (Intrusion Prevention System) and IDS (Intrusion Detection System) solutions by using encrypted communication with the server where Metasploit runs .
- It is also worth noting that Meterpreter will establish an encrypted (TLS) communication channel with the attacker's system.

## Task 02: Meterpreter Flavors

### Description

- Meterpreter payloads are also divided into stagged and inline versions.
- Use msfvenom --list payloads command and grepped "meterpreter" payloads (adding | grep meterpreter to the command line), so the output only shows these.

## Task 03: Meterpreter Commands

### Description

- Typing help on any Meterpreter session (shown by meterpreter> at the prompt) will list all available commands.
- If you run the help command, you will see Meterpreter commands are listed under different categories.
    - Core commands
    - File system commands
    - Networking commands
    - System commands
    - User interface commands
    - Webcam commands
    - Audio output commands
    - Elevate commands
    - Password database commands
    - Timestomp commands

## Task 04: Post-Exploitation with Meterpreter

### Description

- The getuid command will display the user with which Meterpreter is currently running.
- The ps command will list running processes. The PID column will also give you the PID information you will need to migrate Meterpreter to another process.
- Migrating to another process will help Meterpreter interact with it.
- The hashdump command will list the content of the SAM database.
- The shell command will launch a regular command-line shell on the target system. Pressing CTRL+Z will help you go back to the Meterpreter shell.

## Task 05: Post-Exploitation Challenge

### Description

- Commands mentioned previously, such as getsystem and hashdump will provide important leverage and information for privilege escalation and lateral movement.
- Meterpreter is also a good base you can use to run post-exploitation modules available on the Metasploit framework.
- Finally, you can also use the load command to leverage additional tools such as Kiwi or even the whole Python language.

#### Question

What is the computer name?

#### Answer

ACME-TEST

#### Question

What is the target domain?

#### Answer

FLASH

#### Question

What is the name of the share likely created by the user?

#### Answer

speedster

#### Question

What is the NTLM hash of the jchambers user?

#### Answer

69596c7aa1e8daee17f8e78870e25a5c

#### Question

What is the cleartext password of the jchambers user?

#### Answer

Trustno1

#### Question

Where is the "secrets.txt"  file located? (Full path of the file)

#### Answer

c:\Program Files (x86)\Windows Multimedia Platform\secrets.txt 

#### Question

What is the Twitter password revealed in the "secrets.txt" file?

#### Answer

KDSvbsw3849!

#### Question

Where is the "realsecret.txt" file located? (Full path of the file)

#### Answer

c:\inetpub\wwwroot\realsecret.txt

#### Question

What is the real secret?

#### Answer

The Flash is the fastest man alive



