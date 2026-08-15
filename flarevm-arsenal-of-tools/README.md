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

- Prcess Monitor (Procmon)
    - A helpful tool for tracking system activity, especially regarding malware research, troubleshooting, and forensic investigations.
    -  It lets you see, record, and keep track of system and Windows file activity in real-time.
    -  Although this is a standard system process, LSASS may be the target of credential dumping attacks if you are examining logs for indications of malicious activity. Mimikatz and other tools frequently try         to access LSASS memory. 
- Process Explorer (Procexp)
    - Allows you to see the Process of the Parent-child relationship, DLLs loaded, and its path.
- HxD:	Malicious files can be examined or altered via hex editing.
- Wireshark:	Observing and investigating network traffic to look for unusual activity.
- CFF: Explorer	Can generate file hashes for integrity verification, authenticate the source of system files, and validate their validity.
- PEStudio:	Static analysis or studying executable file properties without running the files.
- FLOSS:	Extracts and de-obfuscates all strings from malware programs using advanced static analysis techniques. 

### Description



#### Question

Which tool was formerly known as FireEye Labs Obfuscated String Solver?

#### Answer



#### Question

Which tool offers in-depth insights into the active processes running on your computer?

#### Answer



#### Question

By using the Process Explorer (procexp) tool, under what process can we find smss.exe?

#### Answer



#### Question

Which powerful Windows tool is designed to help you record issues with your system's apps?

#### Answer



#### Question

Which tool can be used for Static analysis or studying executable file properties without running the files?

#### Answer


#### Question

Using the tool PEStudio to open the file cryptominer.bin in the Desktop\Sample folder, what is the sha256 value of the file?

#### Answer


#### Question

Using the tool PEStudio to open the file cryptominer.bin in the Desktop\Sample folder, how many functions does it have?

#### Answer


#### Question

What tool can generate file hashes for integrity verification, authenticate the source of system files, and validate their validity?

#### Answer


#### Question

Using the tool CFF Explorer to open the file possible_medusa.txt in the Desktop\Sample folder, what is the MD5 of the file?

#### Answer


#### Question

Use the CFF Explorer tool to open the file possible_medusa.txt in the Desktop\Sample folder. Then, go to the DOS Header Section. What is the e_magic value of the file?

#### Answer


