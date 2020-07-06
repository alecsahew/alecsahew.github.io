---
layout: post
title:  "Tactics, Techniques and Procedures Part 03"
date:   2020-07-06 10:19:32 +0200
categories: alecsahew github.io EMOTET TRICKBOT RYUK DRIDEX QAKBOT
---

### EMOTET 

* [ AKA TA542, Mummy Spider, GOLD CRESTWOOD ] [TTP-lnk05]
* [ The US-CERT team calls Emotet “the most costly and destructive malware” on the Internet.] [TTP-lnk07]

  [MUMMY SPIDER usually conducts attacks for a few months before ceasing operations for a period of between three and 12 months, before returning with a new variant or version.
   ...
   The latest variant is not deploying a banking Trojan module with web injects, it is currently acting as a ‘loader’ delivering other malware packages. 
   ...
   The primary modules perform reconnaissance on victim machines, drop freeware tools for credential collection from web browsers and mail clients and a spam plugin for self-propagation. 
   ...
   The malware is also issuing commands to download and execute other malware families such as the banking Trojans Dridex and Qakbot.]  [TTP-lnk01]

#### ** The Criminal Ecosystem **
 
  Emotet ditributes different Malware operated by other eCriminals:
  
  * [Mitre Att&ck Emotet.so367 downloader][TTP-lnk05] operated by mummy spider TA542
  * [Mitre Att&ck Dridex.so384 banking trojan][TTP-lnk08] operated by indrik spider TA505
  * [Mitre Att&ck Trickbot.so266 banking trojan ][TTP-lnk09]  ryuk ransomware operated by wizard spider 
  * BokBot banking trojan operated by lunar spider 
  * QBot QakBot  banking trojan 
  
  
  ![ The Criminal Ecosystem](/img/20200706_01.jpg " The Criminal Ecosystem")
                                                                            
....

#### ** The Infection Process Overview **

 ![  The Infection Process Overview](/img/20200706_02.jpg "  The Infection Process Overview")


#### ** The Infection Process **

 ![  The Infection Process ](/img/20200706_03.jpg "  The Infection Process ")



### References 

* [MUMMY SPIDER][TTP-lnk01]
* [US CERT GOV Emotet Malware][TTP-lnk07] 
* [Emotet: Not your Run-of-the-mill Malware][TTP-lnk02]
* [Was Emotet anrichtet – und welche Lehren die Opfer daraus ziehen][TTP-lnk03]
* [2020 CrowdStrike Global Threat Report ][TTP-lnk04]
* [Trojaner Emotet greift Unternehmensnetzwerke an][TTP-lnk06]
* [Mitre Att&ck Emotet][TTP-lnk05]
* [Mitre Att&ck Dridex][TTP-lnk08]
* [Mitre Att&ck Trickbot][TTP-lnk09]


[TTP-lnk01]: https://malpedia.caad.fkie.fraunhofer.de/actor/mummy_spider
[TTP-lnk02]: https://atr-blog.gigamon.com/2020/01/13/emotet-not-your-run-of-the-mill-malware/
[TTP-lnk03]: https://www.heise.de/ct/artikel/Was-Emotet-anrichtet-und-welche-Lehren-die-Opfer-daraus-ziehen-4665958.html
[TTP-lnk04]: https://go.crowdstrike.com/rs/281-OBQ-266/images/Report2020CrowdStrikeGlobalThreatReport.pdf
[TTP-lnk06]: https://www.melani.admin.ch/melani/de/home/dokumentation/newsletter/Trojaner_Emotet_greift_Unternehmensnetzwerke_an.html

[TTP-lnk05]: https://attack.mitre.org/software/S0367/
[TTP-lnk07]: https://www.us-cert.gov/ncas/alerts/TA18-201A
[TTP-lnk08]: https://attack.mitre.org/software/S0384/
[TTP-lnk09]: https://attack.mitre.org/software/S0266/

