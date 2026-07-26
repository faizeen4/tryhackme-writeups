# Wireshark: The Basics

## Task 01: Introduction

### Description

- Wireshark is an open-source, cross-platform network packet analyser tool capable of sniffing and investigating live traffic and inspecting packet captures (PCAP).

#### Question

Which file is used to simulate the screenshots?

#### Answer

http1.pcapng

#### Question

Which file is used to answer the questions?

#### Answer

Exercise.pcapng

## Task 02: Tool Overview

### Description

- Wireshark can be used for multiple purposes, such as:
  
1. Detecting and troubleshooting network problems, such as network load failure points and congestion.
2. Detecting security anomalies, such as rogue hosts, abnormal port usage, and suspicious traffic.
3. Investigating and learning protocol details, such as response codes and payload data.

- Wireshark is not an Intrusion Detection System (IDS). It only allows analysts to discover and investigate the packets in depth.

#### Question

Use the "Exercise.pcapng" file to answer the questions.
Read the "capture file comments". What is the flag?

#### Answer

![Task 2.1](images/wtb-1.png)

TryHackMe_Wireshark_Demo

#### Question

What is the total number of packets?

#### Answer

![Task 2.2](images/wtb-2.png)

58620

#### Question

What is the SHA256 hash value of the capture file?

#### Answer

![Task 2.3](images/wtb-3.png)

f446de335565fb0b0ee5e5a3266703c778b2f3dfad7efeaeccb2da5641a6d6eb

## Task 03: Packet Dissection

### Description

- Packet dissection is also known as protocol dissection, which investigates packet details by decoding available protocols and fields.
- https://github.com/boundary/wireshark/blob/master/doc/README.dissector

#### Question

Use the "Exercise.pcapng" file to answer the questions. View packet number 38. Which markup language is used under the HTTP protocol?

#### Answer

![Task 3.1](images/wtb-4.png)

eXtensible Markup Language

#### Question

What is the arrival date of the packet? (Answer format: Month/Day/Year)

#### Answer

![Task 3.2](images/wtb-5.png)

05/13/2004

#### Question

What is the TTL value?

#### Answer

![Task 3.3](images/wtb-6.png)

47

#### Question

What is the TCP payload size?

#### Answer

![Task 3.4](images/wtb-7.png)

424

#### Question

What is the e-tag value?
(For example: 82ecb-6321-9e904585)

#### Answer

![Task 3.5](images/wtb-8.png)

9a01a-4696-7e354b00


## Task 04: Packet Navigation

### Description

- Wireshark calculates the number of investigated packets and assigns a unique number for each packet.
- Use the "Go" menu and toolbar to view specific packets.
- Use the "Edit --> Find Packet" menu to make a search inside the packets for a particular event of interest.
- Add comments for particular packets that will help the further investigation or remind and point out important/suspicious points for other layer analysts.
- Exporting objects are available only for selected protocol's streams (DICOM, HTTP, IMF, SMB and TFTP).
- Wireshark also detects specific states of protocols to help analysts easily spot possible anomalies and problems. Note that these are only suggestions, and there is always a chance of having false
  positives/negatives.
- Use the "lower left bottom section" in the status bar or "Analyse --> Expert Information" menu to view all available information entries via a dialogue box.  

#### Question

Use the "Exercise.pcapng" file to answer the questions. Search the "r4w" string in packet details. What is the name of artist 1?

#### Answer

![Task 4.1](images/wtb-9.png)

r4w8173

#### Question

Go to packet 12 and read the packet comments. What is the answer?
Note: use md5sum <filename> terminal command to get MD5 hash

#### Answer

![Task 4.2.1](images/wtb-10.1.png)
![Task 4.2.2](images/wtb-10.2.png)
![Task 4.2.3](images/wtb-10.3.png)

911cd574a42865a956ccde2d04495ebf 

#### Question

There is a ".txt" file inside the capture file. Find the file and read it; what is the alien's name?

#### Answer

![Task 4.3.1](images/wtb-11.1.png)
![Task 4.3.2](images/wtb-11.2.png)

PACKETMASTER

#### Question

Look at the expert info section. What is the number of warnings?

#### Answer

![Task 4.4](images/wtb-12.png)

1636

## Task 04: Packet Filtering

### Description

- Capture filters are used for "capturing" only the packets valid for the used filter.
- Display filters are used for "viewing" the packets valid for the used filter.
- Filters are specific queries designed for protocols available in Wireshark's official protocol reference.
- While investigating a capture file, you can click on the field you want to filter and use the "right-click menu" or "Analyse --> Apply as Filter" menu to filter the specific value.
- Suppose you want to investigate a specific packet number and all linked packets by focusing on IP addresses and port numbers. In that case, the "Conversation Filter" option helps you view only the related packets and hide the rest of the packets easily.
-  Streams are shown in a separate dialogue box; packets originating from the server are highlighted with blue, and those originating from the client are highlighted with red.
-  Once you follow a stream, Wireshark automatically creates and applies the required filter to view the specific stream.
-  To filter by protocol name, simply type in the protocol name and hit enter or click on the arrow button at the right hand side of the display filter bar.
-  To filter by protocol port number, you can use the structure "tcp.port == <port number>" or "udp.port == <port number>".
-  To filter for a specific IP, you can use the structure "ip.addr == <IP address>".

#### Question

Use the "Exercise.pcapng" file to answer the questions.
Go to packet number 4. Right-click on the "Hypertext Transfer Protocol" and apply it as a filter.
Now, look at the filter pane. What is the filter query?

#### Answer

![Task 5.1](images/wtb-13.png)

http

#### Question

What is the number of displayed packets?

#### Answer

1089

#### Question

Go to packet number 33790, follow the HTTP stream, and look carefully at the responses.
Looking at the web server's response, what is the total number of artists?

#### Answer

![Task 5.3.1](images/wtb-14.png)
![Task 5.3.2](images/wtb-15.png)

3

#### Question

What is the name of the second artist?

#### Answer

![Task 5.4](images/wtb-16.png)

Blad3










