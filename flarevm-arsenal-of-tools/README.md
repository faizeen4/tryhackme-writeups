 # FlareVM: Arsenal of Tools

## Task 01: Introduction

### Description

- FlareVM, or "Forensics, Logic Analysis, and Reverse Engineering," stands out as a comprehensive and carefully curated collection of specialized tools uniquely designed to meet the specific needs of reverse engineers, malware analysts, incident responders, forensic investigators, and penetration testers.

## Task 02: Arsenal of Tools

### Description

1. Reverse Engineering & Debugging
   - Ghidra - NSA-developed open-source reverse engineering suite.
   - x64dbg - Open-source debugger for binaries in x64 and x32 formats.
   - OllyDbg - Debugger for reverse engineering at the assembly level.
   - Radare2 - A sophisticated open-source platform for reverse engineering.
   - Binary Ninja - A tool for disassembling and decompiling binaries.
   - PEiD - Packer, cryptor, and compiler detection tool.

2. Disassemblers & Decompilers
   - CFF Explorer - A PE editor designed to analyze and edit Portable Executable (PE) files.
   - Hopper Disassembler - A Debugger, disassembler, and decompiler.
   - RetDec - Open-source decompiler for machine code.

3. Static and Dynamic Analysis
   - Process Hacker - Sophisticated memory editor and process watcher.
   - PEview - A portable executable (PE) file viewer for analysis.
   - Dependency Walker - A tool for displaying an executable’s DLL dependencies.
   - DIE (Detect It Easy) - A packer, compiler, and cryptor detection tool.

4. Forensics & Incident Response
    - Volatility - RAM dump analysis framework for memory forensics.
    - Rekall - Framework for memory forensics in incident response.
    - FTK Imager - Disc image acquisition and analysis tools for forensic use.

5. Network Analysis
    - Wireshark - Network protocol analyzer for traffic recording and examination.
    - Nmap - A vulnerability detection and network mapping tool.
    - Netcat - Read and write data across network connections with this helpful tool.

6. File Analysis
    - FileInsight - A program for looking through and editing binary files.
    - Hex Fiend - Hex editor that is light and quick.
    - HxD - Binary file viewing and editing with a hex editor.

7. Scripting & Automation
   - Python - Mainly automation-focused on Python modules and tools.
   - PowerShell Empire - Framework for PowerShell post-exploitation.

8. Sysinternals Suite
   - Autoruns - Shows what executables are configured to run during system boot-up.
   - Process Explorer - Provides information about running processes.
   - Process Monitor -Monitors and logs real-time process/thread activity.

#### Question

Which tool is an Open-source debugger for binaries in x64 and x32 formats?

#### Answer

x64dbg

#### Question

What tool is designed to analyze and edit Portable Executable (PE) files?

#### Answer

CFF Explorer

#### Question

Which tool is considered a sophisticated memory editor and process watcher?

#### Answer

Process Hacker

#### Question

Which tool is used for Disc image acquisition and analysis for forensic use?

#### Answer

FTK Imager

#### Question

What tool can be used to view and edit a binary file?

#### Answer

HxD

## Task 03: Commonly used Tools for Investigation:Overview

### Description

- Prcess Monitor (Procmon)
    - A helpful tool for tracking system activity, especially regarding malware research, troubleshooting, and forensic investigations.
    -  It lets you see, record, and keep track of system and Windows file activity in real-time.
    -  Although this is a standard system process, LSASS may be the target of credential dumping attacks if you are examining logs for indications of malicious activity. Mimikatz and other tools frequently try         to access LSASS memory. 
- Process Explorer (Procexp)
    - Allows you to see the Process of the Parent-child relationship, DLLs loaded, and its path.
- HxD
    - Malicious files can be examined or altered via hex editing.
- Wireshark
    - Observing and investigating network traffic to look for unusual activity.
- CFF Explorer
    - Can generate file hashes for integrity verification, authenticate the source of system files, and validate their validity.
- PEStudio
    - Static analysis or studying executable file properties without running the files.
    - The dual-use nature of PsExec, typically legitimate but suspicious in compromised environments, combined with low to medium indicators and moderately high entropy, makes its presence on a system   concerning, especially if remote code execution is not expected. 
- FLOSS( FLARE Obfuscated String Solver )
    - Extracts and de-obfuscates all strings from malware programs using advanced static analysis techniques. 

#### Question

Which tool was formerly known as FireEye Labs Obfuscated String Solver?

#### Answer

FLOSS

#### Question

Which tool offers in-depth insights into the active processes running on your computer?

#### Answer

Process Explorer

#### Question

By using the Process Explorer (procexp) tool, under what process can we find smss.exe?

#### Answer

![Task 3.1](images/fl1.png)
System

#### Question

Which powerful Windows tool is designed to help you record issues with your system's apps?

#### Answer

Procmon

#### Question

Which tool can be used for Static analysis or studying executable file properties without running the files?

#### Answer

PEStudio

#### Question

Using the tool PEStudio to open the file cryptominer.bin in the Desktop\Sample folder, what is the sha256 value of the file?

#### Answer

![Task 3.2](images/fl2.png)
E9627EBAAC562067759681DCEBA8DDE8D83B1D813AF8181948C549E342F67C0E

#### Question

Using the tool PEStudio to open the file cryptominer.bin in the Desktop\Sample folder, how many functions does it have?

#### Answer

![Task 3.3](images/fl3.png)
102

#### Question

What tool can generate file hashes for integrity verification, authenticate the source of system files, and validate their validity?

#### Answer

CFF Explorer

#### Question

Using the tool CFF Explorer to open the file possible_medusa.txt in the Desktop\Sample folder, what is the MD5 of the file?

#### Answer

![Task 3.4](images/fl4.png)
646698572AFBBF24F50EC5681FEB2DB7

#### Question

Use the CFF Explorer tool to open the file possible_medusa.txt in the Desktop\Sample folder. Then, go to the DOS Header Section. What is the e_magic value of the file?

#### Answer

![Task 3.5](images/fl5.png)
5A4D

## Task04 : Analyzing Malicious File!

#### Description

-  Static Analysis using PEStudio and FLOSS
       - Target : windows.exe in C:\Users\Administrator\Desktop\Sample folder
- Analyze with Process Explorer and Process Monitor
       - Target : cobaltstrike.exe in C:\Users\Administrator\Desktop\Sample folder

#### Question

Using PEStudio, open the file windows.exe. What is the entropy value of the file windows.exe?

#### Answer

![Task 4.1](images/fl6.png)
7.999

#### Question

Using PEStudio, open the file windows.exe, then go to manifest (administrator section). What is the value under requestedExecutionLevel?

#### Answer

![Task 4.2](images/fl7.png)
requireAdministrator

#### Question

Which function allows the process to use the operating system's shell to execute other processes?

#### Answer

![Task 4.3](images/fl8.png)
set_UseShellExecute

#### Question

Which API starts with R and indicates that the executable uses cryptographic functions?

#### Answer

![Task 4.4](images/fl9.png)
RijndaelManaged

#### Question

What is the Imphash of cobaltstrike.exe?

#### Answer

![Task 4.5](images/fl10.png)
92EEF189FB188C541CBD83AC8BA4ACF5

#### Question

What is the defanged IP address to which the process cobaltstrike.exe is connecting?

#### Answer

![Task 4.6](images/fl11.png)
47[.]120[.]46[.]210

#### Question

What is the destination port number used by cobaltstrike.exe when connecting to its C2 IP Address?

#### Answer

![Task 4.7](images/fl12.png)
81

#### Question

During our analysis, we found a process called cobaltstrike.exe. What is the parent process of cobaltstrike.exe? 

#### Answer

![Task 4.8](images/fl13.png)
explorer.exe
