# Nmap: The Basics

## Task 01: Introduction

### Description

- Nmap is an open-source network scanner that was first published in 1997. Since then, plenty of features and options have been added. It is a powerful and flexible network scanner that can be adapted to various scenarios and setups.

## Task 02: Who Is Online

### Description

- IP range using -: If you want to scan all the IP addresses from 192.168.0.1 to 192.168.0.10, you can write 192.168.0.1-10
- IP subnet using /: If you want to scan a subnet, you can express it as 192.168.0.1/24, and this would be equivalent to 192.168.0.0-255
- Hostname: You can also specify your target by hostname, for example, example.thm
- When scanning the local network, where we are connected via Ethernet or WiFi, we can look up the MAC addresses of the devices. Consequently, we can figure out the network card vendors, which is beneficial information as it can help us guess the type of target device(s). EExample: nmap -sn 192.168.66.0/24
-  We can have more control over how Nmap discovers live hosts such as -PS[portlist], -PA[portlist], -PU[portlist] for TCP SYN, TCP ACK, and UDP discovery via the given ports.
-  As a final point, Nmap offers a list scan with the option -sL. This scan only lists the targets to scan without actually scanning them.

#### Question

What is the last IP address that will be scanned when your scan target is 192.168.0.1/27?

#### Answer

192.168.0.31

## Task 03: Port Scanning:Who Is Listening

### Description

- The connect scan can be triggered using -sT. It tries to complete the TCP three-way handshake with every target TCP port. If the TCP port turns out to be open and Nmap connects successfully, Nmap will tear down the established connection.
- Unlike the connect scan, which tries to connect to the target TCP port, i.e., complete a three-way handshake, the SYN scan only executes the first step: it sends a TCP SYN packet. Consequently, the TCP three-way handshake is never completed. The advantage is that this is expected to lead to fewer logs as the connection is never established, and hence, it is considered a relatively stealthy scan. You can select the SYN scan using the -sS flag.
- Nmap offers the option -sU to scan for UDP services. Because UDP is simpler than TCP, we expect the traffic to differ.
- -F is for Fast mode, which scans the 100 most common ports (instead of the default 1000).
- -p[range] allows you to specify a range of ports to scan.

#### Question

How many TCP ports are open on the target system at 10.49.133.88?

#### Answer

6

#### Question

Find the listening web server on 10.49.133.88 and access it with your browser. What is the flag that appears on its main page?

#### Answer

THM{SECRET_PAGE_38B9P6}

## Task 04: Version Detection:Extract More Information

### Description

- You can enable OS detection by adding the -O option
- You discovered several open ports and want to know what services are listening on them. -sV enables version detection.
- -A enables OS detection, version scanning, and traceroute, among other things.
- -Pn	Scan hosts that appear to be down

#### Question

What is the name and detected version of the web server running on 10.49.133.88?

#### Answer

lighttpd 1.4.74

## Task 05: Timing:How Fast is Fast

### Description

- Nmap gives you six timing templates, and the names say it all: paranoid (0), sneaky (1), polite (2), normal (3), aggressive (4), and insane (5)
- A second helpful option is the number of parallel service probes. The number of parallel probes can be controlled with --min-parallelism <numprobes> and --max-parallelism <numprobes>.
- A similar helpful option is the --min-rate <number> and --max-rate <number>.
- The last option we will cover in this task is --host-timeout <time>. This option specifies the maximum time you are willing to wait, and it is suitable for slow hosts or hosts with slow network connections.

#### Question

What is the non-numeric equivalent of -T4?

#### Answer
//no pic
-T aggressive


## Task 06: Output:Controlling What You See

### Description

- The -v option is more than enough for verbose output; however, if you are still unsatisfied, you can increase the verbosity level by adding another “v” such as -vv or even -vvvv. You can also specify the verbosity level directly, for example, -v2 and -v4. You can even increase the verbosity level by pressing “v” after the scan already started.
- If all this verbosity does not satisfy your needs, you must consider the -d for debugging-level output. Similarly, you can increase the debugging level by adding one or more “d” or by specifying the debugging level directly.
- ou can select the scan report format as follows:
    - -oN <filename> - Normal output
    - -oX <filename> - XML output
    - -oG <filename> - grep-able output (useful for grep and awk)
    - -oA <basename> - Output in all major formats

#### Question

What option must you add to your nmap command to enable debugging?

#### Answer
//no pic
-d


 
