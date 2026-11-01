Operation PacketLens

Network Traffic Analysis and Connectivity Troubleshooting | Wireshark

1. Project Overview

Operation PacketLens is a network traffic analysis and connectivity troubleshooting project performed using Wireshark.

The project consists of three experiments covering TCP connection establishment, HTTP communication, DNS query and response analysis, and ICMP connectivity testing.

Packet captures were analysed using Wireshark display filters, while Command Prompt was used to generate and verify network traffic.

2. Project Objectives

- Analyse TCP connection establishment and termination.
- Observe HTTP request and response communication.
- Examine DNS queries and responses.
- Understand A and AAAA DNS record lookups.
- Test network connectivity using ICMP.
- Identify and interpret packets using Wireshark display filters.

3. Tools Used

- Wireshark
- Windows Command Prompt
- Network protocols: TCP, HTTP, DNS and ICMP

---

Experiment 1: TCP Handshake and HTTP Analysis

Objective

To observe TCP connection establishment, HTTP request-response communication, and connection termination using Wireshark.

Display Filter:

tcp.port == 80

Procedure

1. Opened Wireshark and started capturing network traffic.
2. Generated HTTP traffic from the computer.
3. Applied the display filter "tcp.port == 80".
4. Examined the TCP handshake, HTTP request, server response and connection termination packets.
5. Saved the packet capture and screenshot as project evidence.

IP Address and Port Details

Parameter| Value
Local IP address| 10.108.149.233
Remote IP address| 23.48.245.152
Client TCP port| 50666
Remote TCP port| 80

Observations and Results

The captured traffic showed:

- TCP three-way handshake: SYN, SYN/ACK and ACK packets established the TCP connection.
- HTTP request: The client sent "GET /connecttest.txt HTTP/1.1".
- HTTP response: The server returned "HTTP/1.1 200 OK (text/plain)", indicating a successful response.
- Connection termination: FIN/ACK packets showed the connection closing sequence.

Evidence Files

- Packet capture: "OPD_PacketLense_01"
- Wireshark screenshot: "OPD_PacketLense_01ss"

Figure 1: TCP and HTTP Traffic Analysis

Caption: Wireshark capture showing the TCP three-way handshake, HTTP GET request, successful HTTP 200 OK response and connection termination packets.

Conclusion

This experiment demonstrated how Wireshark can be used to inspect TCP connection establishment, identify HTTP requests and responses, and observe connection termination. The captured traffic confirmed successful HTTP communication during the test.

---

Experiment 2: DNS Query and Response Analysis

Objective

To analyse DNS queries and responses in Wireshark and observe how a domain name is resolved to IP addresses.

Tools Used: Wireshark and Command Prompt

Display Filter:

dns.qry.name contains "example.com"

Procedure

1. Started a packet capture in Wireshark.
2. Opened Command Prompt and executed "nslookup example.com".
3. Returned to Wireshark and applied the DNS display filter.
4. Examined the DNS queries and their corresponding responses.
5. Saved the packet capture and screenshot as project evidence.

Network Details

Parameter| Value
Domain queried| example.com
Local computer IP| 10.108.149.233
DNS server| 10.108.149.18

Observations and Results

The captured traffic showed DNS queries for both A records (IPv4 addresses) and AAAA records (IPv6 addresses).

The A-record response included the following IPv4 addresses:

- "172.66.147.243"
- "104.20.23.154"

The corresponding DNS responses demonstrated how the DNS server provided address information for the requested domain.

Evidence Files

- Packet capture: "ODP_02_DNS_Analysis"
- Wireshark screenshot: "ODP_02_DNS_Analysis_ss"

Figure 2: DNS Query and Response Analysis

Caption: Wireshark capture showing DNS queries and corresponding responses for example.com, including A and AAAA record lookups.

Conclusion

This experiment demonstrated how DNS translates domain names into IP addresses and how Wireshark can be used to inspect DNS queries, record types and responses.

---

Experiment 3: ICMP Connectivity Testing

Objective

To test network connectivity to "1.1.1.1" and use Wireshark to analyse ICMP Echo Request and Echo Reply packets.

Tools Used: Wireshark and Command Prompt

Wireshark Display Filter:

icmp

Procedure

1. Opened Wireshark and started capturing network traffic.
2. Opened Command Prompt and executed "ping 1.1.1.1".
3. Observed the ping responses and packet-loss statistics.
4. Applied the "icmp" display filter in Wireshark.
5. Examined ICMP Echo Request packets sent by the local computer and corresponding Echo Reply packets received from "1.1.1.1".
6. Saved the packet capture and screenshots as project evidence.

Network Details

Parameter| Value
Local computer IP| 10.108.149.233
Destination IP| 1.1.1.1
Protocol analysed| ICMP

Command Prompt Results

Measurement| Result
Packets sent| 4
Packets received| 4
Packets lost| 0
Packet loss| 0%
Minimum response time| 37 ms
Maximum response time| 237 ms
Average response time| 99 ms

Observations and Results

The ping test successfully received replies from "1.1.1.1", with 0% packet loss during the test.

In Wireshark, the "icmp" filter displayed Echo Request packets travelling from the local computer to the destination and Echo Reply packets travelling back.

These observations confirmed successful connectivity during the capture.

No network fault was confirmed during this experiment; it was a connectivity verification and packet-analysis test.

Evidence Files

- Packet capture: "OPD_03_ICMP_Connectivity_Test"
- Wireshark screenshot: "OPD_03_ICMP_Connectivity_Test_ss"
- Command Prompt screenshot: "OPD_03_ICMP_Connectivity_Test_command_prompt_ss"

Figure 3: ICMP Connectivity Test

Caption: Wireshark capture showing ICMP Echo Request and Echo Reply packets between the local computer and 1.1.1.1.

Figure 4: Command Prompt Connectivity Results

Caption: Command Prompt output showing four successful ping replies from 1.1.1.1, with zero packet loss and an average response time of 99 ms, alongside DNS resolution results for example.com.

Conclusion

This experiment demonstrated how to verify IP connectivity using the "ping" command and analyse ICMP traffic in Wireshark. The successful replies and zero packet loss confirmed that the destination was reachable during the test.

---

4. Overall Project Outcome

Successfully performed three network analysis experiments using Wireshark.

The project demonstrated practical analysis of TCP handshakes, HTTP request-response communication, DNS resolution and ICMP connectivity. Packet captures and screenshots were saved as evidence of the experiments.

5. Skills Practised

- Wireshark packet capture and analysis
- TCP three-way handshake analysis
- HTTP request and response inspection
- DNS query and response analysis
- A and AAAA record identification
- ICMP Echo Request and Echo Reply analysis
- Network connectivity verification
- Command Prompt networking utilities
- Display filter application and packet interpretation

6. Repository Structure

Operation-PacketLens/
│
├── README.md
│
├── packet-captures/
│   ├── Experiment-1-TCP-HTTP/
│   ├── Experiment-2-DNS/
│   └── Experiment-3-ICMP/
│
└── screenshots/
    ├── Experiment-1-TCP-HTTP/
    ├── Experiment-2-DNS/
    └── Experiment-3-ICMP/

7. Project Scope

This project is an educational network traffic analysis exercise. The experiments were conducted to understand protocol behaviour and verify connectivity using captured network traffic.

---

Project: Operation PacketLens
Category: Network Traffic Analysis and Connectivity Troubleshooting
Tool: Wireshark
Experiments: 3
