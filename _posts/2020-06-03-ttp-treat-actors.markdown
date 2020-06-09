---
layout: post
title:  "Tactics, Techniques and Procedures Part 02"
date:   2020-06-03 11:19:32 +0200
categories: alecsahew github.io TTP  Treat Actors
---

### Treat Actors And Their Tactics, Techniques And Procedures  

#### **Treat Actors Targeting Financial Organizations**
#### [ANUNAK][TTP-lnk105]
* [group.G0008] [TTP-lnk106]
* **AKA**: Carbanak, Carbon Spider, FIN7, GOLD NIAGARA 
* **TARGET**: Groups targeting financial organizations or people with significant financial assets. 
* **MALWARE**: AveMariaRAT Carbanak

#### [Lazarus Group - APT37 - APT38] [TTP-lnk107]
* [group.G0032][TTP-lnk108]
* group.G0082
* group.G0067
* **AKA**: Operation DarkSeoul, Dark Seoul, Hidden Cobra, Hastati Group, Andariel, Unit 121, Bureau 121, NewRomanic Cyber Army Team, Bluenoroff, Subgroup: Bluenoroff, Group 77, Labyrinth Chollima, Operation Troy, Operation GhostSecret, Operation AppleJeus, APT38, APT 38, Stardust Chollima, Whois Hacking Team, Zinc, Appleworm, Nickel Academy, APT-C-26, NICKEL GLADSTONE 
* **TARGET**: The group mainly targets banks and financial institutions. APT38 is known to have significant overlap, and the name Lazarus Group. Some organizations track this groups such as Bluenoroff.
* **MALWARE**: DarkComet 

#### **Treat Actors Targeting Industries** 
#### [APT33] [TTP-lnk103]
* [group.G0064] [TTP-lnk104]
* **AKA**: Elfin, MAGNALLIUM, Refined Kitten, HOLMIUM, COBALT TRINITY 
* **TARGET**: organizations across multiple industries in the United States, Saudi Arabia, and South Korea, with a particular interest in the aviation and energy sectors.
* **MALWARE**: NanoCore (RAT) Remcos (RAT)

#### **Treat Actors Targeting Western Governments**
#### [APT28][TTP-lnk109] [APT29] [TTP-lnk111]
* [group.G0007] [TTP-lnk110]
* [group.G0016] [TTP-lnk112]
* **AKA**: Dukes, Group 100, Cozy Duke, CozyDuke, EuroAPT, CozyBear, CozyCar, Cozer, Office Monkeys, OfficeMonkeys, APT29, Cozy Bear, The Dukes, Minidionis, SeaDuke, Hammer Toss, YTTRIUM, Iron Hemlock, Grizzly Steppe 
* **TARGET**: This group highly dedicated and organized cyberespionage group. They primarily target Western governments and related organizations.

#### **Treat Actors: Criminals Entities**

#### [SWEED] [TTP-lnk101] 
* **TARGET**: primarily targets their victims with stealers and remote access trojans (RAT)
* **MALWARE**: Formbook, Lokibot and AgentTesla 
* **METHODS**: use of spear-phishing emails with malicious attachments
* **PROGRAMMING LANGUAGE**: .NET

#### [MUMMY SPIDER] [TTP-lnk113] 
* **AKA** TA542, Mummy Spider, GOLD CRESTWOOD 
* **TARGET**:  it was used to target the banking sector. Nowadays Emotet is mostly seen as infrastructure as a service for content delivery acting for downloading other malware packages 
* **MALWARE**: [Emotet.S0367] [TTP-lnk114] or Geodo 
* **PACKEGES** TrickBot, ransomware Ryuk


### References 

* [MITRE ATT&CK Framework][TTP-lnk01]
* [The Pyramid of Pain][TTP-lnk02]
* [ABUSE.ch][TTP-lnk03]



[TTP-lnk01]: https://attack.mitre.org/
[TTP-lnk02]: https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html
[TTP-lnk03]: https://bazaar.abuse.ch

[TTP-lnk101]: https://malpedia.caad.fkie.fraunhofer.de/actor/sweed

[TTP-lnk103]: https://malpedia.caad.fkie.fraunhofer.de/actor/apt33
[TTP-lnk104]: https://attack.mitre.org/groups/G0064/

[TTP-lnk105]: https://malpedia.caad.fkie.fraunhofer.de/actor/anunak
[TTP-lnk106]: https://attack.mitre.org/groups/G0008/

[TTP-lnk105]: https://malpedia.caad.fkie.fraunhofer.de/actor/lazarus_group
[TTP-lnk106]: https://attack.mitre.org/groups/G0032/

[TTP-lnk107]: https://malpedia.caad.fkie.fraunhofer.de/actor/lazarus_group
[TTP-lnk108]: https://attack.mitre.org/groups/G0082/

[TTP-lnk109]: https://malpedia.caad.fkie.fraunhofer.de/actor/sofacy
[TTP-lnk110]: https://attack.mitre.org/groups/G0007/

[TTP-lnk111]: https://malpedia.caad.fkie.fraunhofer.de/actor/apt_29
[TTP-lnk112]: https://attack.mitre.org/groups/G0016/



[TTP-lnk113]: https://malpedia.caad.fkie.fraunhofer.de/actor/mummy_spider
[TTP-lnk114]: https://attack.mitre.org/software/S0367/

