---
layout: post
title:  "Analysing Honeypots Running In T-PoT Part 04"
date:   2020-04-20 11:58:32 +0200
categories: alecsahew github.io Cowrie T-Pot Honeypot Analysis
---

### What We Can Learn From 24 Hours Attack in COVID-19 Times

#### Conclusions 

* Locations: determine only the location of the device that interacted. An attacker may be interacting through a VPN or VPS located in another country. 

* IP address: block malicious domains and IP addresses 

* IoT Devices: consider segregating them and firewalling them

* Ports Non-Public Listening: consider putting them (RDP, sshd etc.) behind a VPN or SSH Tunnel
* Ports telnet/ssh:  disable telnet and move your SSH, RDP to non-standard ports  

* Login: use strong SSH passwords. Limit failed SSH login attempts. Use key authentication.   
* Login: disable/rename root or admin login or only allow it with private key authentication

* Brute Force Attacks: protect against them using a tool like fail2ban

* DDoS Denial of Service Attacks: use an IDS/IPS like Snort/Suricata with a ruleset to detect and block traffic generated by a DDoS malware

* SIEM: Integrate e.g. XOR DDOS Bot data into SIEM, implement alerts within a SIEM application 


