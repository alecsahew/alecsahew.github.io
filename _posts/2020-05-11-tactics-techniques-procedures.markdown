---
layout: post
title:  "Tactics, Techniques and Procedures"
date:   2020-05-11 17:19:32 +0200
categories: alecsahew github.io MITRE ATT&CK MIRAI BOTNET 
---

### Mapping APT Profiles to MITRE ATT&CK Framework with MIRAI 

#### **TTP and The Pyramide Of Pain**

 The concept of  "The Pyramid of Pain"  was introduced by David J Bianco in 2013.
 The pyramid describes the usefulness of your threat intelligence and also the difficulty to obtain that information.

 ![The Pyramid of Pain](/img/20200509_03.jpg "The Pyramid of Pain")
                                                                            
 David J Bianco writes:
                                  
 *"To illustrate this concept, I have created what I like to call the Pyramid of Pain. 
 This simple diagram shows the relationship between the types of indicators 
 you might use to detect an adversary's activities and how much pain it will cause them
 when you are able to deny those indicators to them. Let's examine this diagram in more detail.*
                                                                                                
 ...
 *Finally, at the apex are the TTPs.  When you detect and respond at this level, 
 you are operating directly on adversary behaviors, not against their tools.* 
                                                                                         
 ...
 *From a pure effectiveness standpoint, this level is your ideal. 
 If you are able to respond to adversary TTPs quickly enough, 
 you force them to do the most time-consuming thing possible: learn new behaviors."*



#### **TTP and MITRE ATT&CK**

The MITRE ATT&CK framework is an open knowledgedatabase that contains adversary tactics and techniques. 
Those are based on real world observations. 
ATT&CK tracks and profiles current and past threats so that you can have a better understanding about threats you may face.  

#### **MIRAI: The Blueprint**

  ![Mirai Blueprint](/img/20200511_01.jpg "Mirai Blueprint")

#### **MIRAI: The Open Source IoT Botnet**
MIRAI made security automation a must

#### Centralized Services / C2 Infrastructure

#### --> C2 Server  (RED)
Provides multi-tenant "customer" API + MySQL database ( Image I + II + III )

#### --> scanListen at port 48101 ( written in Golang ) (RED and GREEN)
Listens on port 48101 for REPORTS from bot (3) and passes IP:PORT USERNAME:PASSWORD ARCHITECTURE to LoadService (4)

#### --> LoadService ( written in C/C++ ) (RED and GREEN)
LoadService (4) takes the string to get access to the shell command on the new victim and loads the bot (5)

#### --> MIRAI Client Bot ( written in C/C++ ) (DARK)
 * increases resistance against R.E.
 * strings are encrypted in tables
 * no persistence

Once loaded (5) the bot client will 

* (a) **register** to C2 (6)
* (b) start **scanning** for other victims (7) on ports 23 / 2323
* (c) **brute force** 10 randomly selected user: password
* (d) **passes** reports to scanListen (3)
* (e) **wait** for commands from C2
* (f) **initialize** ( execute ) DDoS attacks  ( 10 different )
* (g) **teminate** process listening on port 23 / 23 / 80
* (h) **kill** known bot process

#### --> Attack Payload

1. f generic UDP Flood
2. f Plain UDP flood
3. f SYN flood
4. f ACK flood 
5. f STOMP
6. f GREIP flood
7. f GREETH flood
8. f VSE flood
9. f HTTP flood
10. f DNS flood ( DNS Water Torture Attack )

**MIRAI DOES NOT have the function stop/interrupt the attack**

#### **MIRAI: The Mapping** TACTICS&TECHNIQUE

|Rf  |Tactics PreAtt&ck                        |TECHNIQUE                                            |ID   |DESCRIPTION
|----|-----------------------------------------|-----------------------------------------------------|-----|------------------------
|RED |TA0022 Establish&Maintain Infrastructure |Acquire and/or use 3rd party infrastructure services |T1329|bots are available for rent or purchase 
|RED |TA0022 Establish&Maintain Infrastructure |Obtain booter/stressor subscription|T1369|Configure and setup services 

|Rf  |Tactics Enterprise       |TECHNIQUE                              |ID   |DESCRIPTION
|----|-------------------------|---------------------------------------|-----|----------------------------------------------------
|a-b |TA0011 Command&Control   |Commonly Used Port                     |T1043|bot communicates with C&C on port 23
|c   |TA0007 Discovery         |Network Service Scanning               |T1046|bot starts scanning for other victims on ports 23/2323
|c   |TA0001 Initial Access    |Exploits PublicFacing Application      |T1190|bot compromises IoT devices by exploiting SSH/Telnet
|d   |TA0006 Credential Acc    |Brute Force                            |T1110|bot brute force 10 randomly selected user:password
|f   |TA0040 Impact            |Network  Denial Of Service             |T1498|bot can conduct network denial-of-service attack
|f   |TA0040 Impact            |EndPoint Denial Of Service             |T1499|bot can conduct HTTP flood attack

#### **MIRAI: The Mapping**  MITAGATION 

|TECHNIQUE ID | MITAGATION             |ID   |DESCRIPTION
|--------|-----------------------------|-----|----------------------------------------------------------
|T1043|Network Intrusion Prevention |M1031|Use intrusion detection signatures to block traffic at network boundaries. 
|T1046|Network Segmentation         |M1030|Architect sections of the network to isolate critical systems, functions, or resources
|T1190|Application Isolation and Sandboxing|M1048|Restrict execution of code to a virtual environment on or in transit to an endpoint system.
|T1190|Exploit Protection|M1050|Use capabilities to detect and block conditions that may lead to or be indicative of a software exploit occurring
|T1190|Network Segmentation |M1030|Architect sections of the network to isolate critical systems, functions, or resources
|T1190|Privileged Account Management|M1026|Manage the creation, modification, use, and permissions associated to privileged accounts, including SYSTEM and root.
|T1190|Update Software|M1051|Perform regular software updates to mitigate exploitation risk.
|T1190|Vulnerability Scanning|M1016|Vulnerability scanning is used to find potentially exploitable software vulnerabilities to remediate them  
|T1110|Account Use Policies|M1036| Configure features related to account use like login attempt lockouts, specific login times, etc
|T1110|Multi-factor Authentication|M1032|Use two or more pieces of evidence to authenticate to a system
|T1110|Password Policies |M1027|Set and enforce secure password policies for accounts.
|T1498|Filter Network Traffic|M1037| Use network appliances to filter ingress or egress traffic and perform protocol-based filtering
|T1499|Filter Network Traffic|M1037| Use network appliances to filter ingress or egress traffic and perform protocol-based filtering   



### References 

* [MITRE ATT&CK Framework][TTP-lnk01]
* [The Pyramid of Pain][TTP-lnk02]
* [Pyramid of Pain Vs. The Iceberg of Inspection][TTP-lnk04]
* [Heightened DDoS Threat Posed by Mirai and Other Botnets][TTP-lnk03]



[TTP-lnk01]: https://attack.mitre.org/
[TTP-lnk02]: https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html
[TTP-lnk04]: https://inquest.net/blog/2020/01/24/Pyramid-of-Pain-Vs-Iceberg-of-Inspection

[TTP-lnk03]: https://www.us-cert.gov/ncas/alerts/TA16-288A






