---
layout: post
title:  "Analysing Honeypots Running In T-PoT Part 02"
date:   2020-04-06 16:58:32 +0200
categories: alecsahew github.io Cowrie T-Pot Honeypot Analysis
---

### What We Can Learn From 24 Hours Attack in COVID-19 Times.  Analysing Cowrie

#### Distribution Attack By Protocoll

|Destination Port | Protocoll	  |Count |           
|:----------------|:--------------|:-----|
|23				  |telnet		  |342|
|22				  |ssh			  |22|

#### Distribution By User/Password By Successful Login
* Brute Force attack if field PASSWORD empty

|USER         |PASSWORD  |PROTOCOL  |Successfull Login Count |
|:--------  --|:---------|:---------|:-----------------------|
|root         |          |telnet    |38|
|admin        |          |telnet    |21|
|default      |default   |telnet    |18|
|guest        |          |telnet    |3|
|service      |service   |telnet    |2|
|supervisor   |          |telnet    |2|
|tech         |tech      |telnet    |1|

#### TOP 10 - Distribution By ASN, ORGANISATION, COUNTRY, COUNT 

|ASN    |ORGANISATION           | COUNTRY       |Count     |
|:------|:----------------------|:--------------|:---------|
|36866	|JTL                    |Kenya          |49
|58542	|Yueyang 		        |China		    |36
|8452	|TE Data 		        |Egypt		    |28
|6057	|Administracion Nacional de Telecomunicaciones|Uruguay|27
|4134	|Chinanet 		        |China		    |22
|4766	|Korea Telecom	        |Republic of Korea|8
|7552	|Viettel Corporation    |Vietnam        |8
|4837	|CNCGROUP China169 Backbone |China      |6
|45899	|VNPT Corp		        |Vietnam    	|6
|43234	|TalkTalk 		        |United Kingdom |5


#### The Attacker's Action: Example 1

|COWRIE                 |INPUT                  |COMMENT                                 |
|:----------------------|:----------------------|:---------------------------------------|
cowrie.session.connect	|						||		
cowrie.login.success	|admin/admin			||	
cowrie.session.params	|						||
cowrie.command.input	|enable					|allow access to privileged-mode commands| 	
cowrie.command.input	|sh						|attempt to run a Bourne shell|	
cowrie.command.input	|shell					|attempt to run a Bourne shell| 	
cowrie.command.failed	|shell					||
cowrie.command.input	|linuxshell				|attempt to run a Bourne shell| 	
cowrie.command.failed	|linuxshell				||
cowrie.command.input	|system					|attempts to navigate to a menu| 	
cowrie.command.failed	|system					||
cowrie.command.input	|/bin/busybox CORONA	|| 
cowrie.log.closed		|						||
cowrie.session.closed	|						||


#### The Attacker's Action: Example 2

|COWRIE.                |INPUT                  |COMMENT                                 |
|:----------------|:----------------------|:---------------------------------------|
|login.success	|guest/friend||		
|session.params	|||		
|command.input	|enable|allow access to privileged-mode commands|		
|command.input	|system|attempts to navigate to a menu|		
|command.failed	|system||	
|command.input	|shell|attempt to run a Bourne shell|		
|command.failed	|shell||		
|command.input	|sh|attempt to run a Bourne shell|		
|command.input	|cat /proc/mounts;|trying to search for writable mounts where to download the binary|
|command.input	|/bin/busybox REXOR|trying to find the end of the command line's output|
|command.input	|cd /dev/shm; cat .s \| cp /bin/echo .s;|copy the echo binary|
|command.input	|/bin/busybox REXOR|trying to find the end of the command line's output|
|command.input	|tftp; wget;|check availability for tftp and wget|
|command.input	|/bin/busybox REXOR|trying to find the end of the command line's output|
|command.input	|dd bs=52 count=1 if=.s \| cat .s \| while read i; do echo $i; done < .s|
|command.failed	|while read i| trying to determine the target's processor architecture|		
|command.input	|/bin/busybox REXOR|trying to find the end of the command line's output|
|command.input	|rm .s; exit||		
|log.closed	|||	
|session.closed	|||		

### References
* Botnets: Architectures, Countermeasures, and Challenges(CRC Series in Security, Privacy and Trust) 14-October-2019 

[Honeypots and the Internet of Things 1][iot01-lnk]                   
[Honeypots and the Internet of Things 2][iot02-lnk]                    
[Honeypots and the Internet of Things 2 Translation][iot22-lnk] 


[iot01-lnk]:https://securelist.com/honeypots-and-the-internet-of-things/78751/
[iot02-lnk]:https://www.venustech.com.cn/article/1/11495.html
[iot22-lnk]:https://translate.google.com/translate?hl=en&sl=auto&tl=en&u=https%3A%2F%2Fwww.venustech.com.cn%2Farticle%2F1%2F11495.html

