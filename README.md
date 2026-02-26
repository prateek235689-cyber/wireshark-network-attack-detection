📌 Network Attack Detection and Investigation Using Wireshark

📖 Project Overview:
This project demonstrates how common network reconnaissance techniques can be simulated and detected in a controlled SOC lab environment.

Objective:
The objective was to understand how ICMP host discovery and TCP SYN port scanning appear at the packet level and how such activity can be identified from a Security Operations Center (SOC) perspective.

🎯 Objectives:
Simulate reconnaissance techniques in a lab environment
Capture and analyze packet-level traffic
Identify suspicious TCP flag behavior
Detect port scanning indicators
Develop SOC-oriented analytical skills

🧪 Lab Environment:
Attacker Machine: Kali Linux (VirtualBox).
Target Machine: Windows 11.
Monitoring Tool: Wireshark.
Scanning Tool: Nmap.
Network Mode: Bridged / Host-Only (Same Subnet).

Both virtual machines were configured within the same subnet to enable successful communication before executing attack simulations.

🔍 Attack 1 – ICMP Host Discovery / Ping Sweep:

Commands Used:
ping <Windows_IP>
Wireshark Filter: icmp

Key Observations:
Continuous ICMP Echo Requests from attacker machine.
Corresponding Echo Replies from target system.
Traffic observed at regular intervals.
No packet loss detected.


🔍 Attack 2 – TCP SYN Port Scanning:

Commands Used:
nmap <Windows_IP>
nmap -sS <Windows_IP>
Wireshark Filter: tcp.flags.syn == 1 && tcp.flags.ack == 0

Key Observations:
Multiple TCP SYN packets targeting different ports.
RST responses for closed ports.
SYN-ACK responses for open ports.
Incomplete TCP handshakes.
High packet volume within short duration.


Indicators of Compromise (IOCs):
High SYN packet rate.
Sequential port probing.
Single source IP scanning multiple services.
Incomplete session establishment.

🚨 Risk Assessment
The detected activity is classified as Medium Risk due to active reconnaissance behavior. While no exploitation occurred, such scanning behavior often precedes targeted attacks.

📊 Key Learning Outcomes:
Practical packet-level traffic analysis.
Understanding TCP flag behavior.
Identifying reconnaissance indicators.
Differentiating normal vs suspicious traffic.
Thinking from a SOC analyst perspective.

Prateek Gupta
Cyber Security Student | Aspiring SOC Analyst
