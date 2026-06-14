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

- A bind shell will bind a port on the compromised system and listen for a connection; when this connection occurs, it exposes the shell session so the attacker can execute commands remotely.
  
#### Question

What type of shell opens a specific port on the target for incoming connections from the attacker?

#### Answer

Bind Shell

#### Question

Listening below which port number requires root access or privileged permissions?

#### Answer

1024
