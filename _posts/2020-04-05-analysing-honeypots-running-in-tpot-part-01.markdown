---
layout: post
title:  "Analysing Honeypots Running In T-PoT Part 01"
date:   2020-04-05 14:58:32 +0200
categories: alecsahew github.io T-Pot Honeypot Analysis
---

<h3>What We Can Learn From 24 Hours Attack in COVID-19 Times. Overview</h3>

<h4>Distribution By Honeypots Attacks</h4>

<table>
<tr>
<td>40,961 Dionaea</td>
<td>18,309 Honeytrap</td>
<td>2,526  Cowrie</td>
<td>141    Adbhoney</td>
<td>119    Rdpy</td>
<td>74     Tanner</td>
<td>17     Ciscoasa</td>
<td>6      Mailoney</td>
<td>3      ConPot</td>
<td>2      ElasticPot</td>
</tr>
</table>

                                                              
<h4>Geographic Distribution By Provider By Countries > 100 Attacks</h4>

|ASN    |Organisation                       |Country            | Count |
|:------|:----------------------------------|:------------------|:------|
|14061  |Digital Ocean, Inc.      			|Germany	    	|12413|
|14061	|Digital Ocean, Inc.	  			|United States  	|139|
|14061	|Digital Ocean, Inc.	  			|United Kingdom		|3|
|14061	|Digital Ocean, Inc.	  			|Canada				|1|
|24164	|YEONG JIA LEH CABLE TV CO., LTD.	|Taiwan 			|11745|
|9829	|National Internet Backbone	        |India				|11642|
|12714	|Net By Net Holding LLC	            |Russia				|6325|
|45899	|VNPT Corp	                        |Vietnam			|2178|
|7623	|Gyeongbuk Cable TV	                |Republic of Korea	|1799|
|12389	|PJSC Rostelecom					|Russia				|1789|
|8048	|CANTV Servicios, Venezuela			|Venezuela			|1569|
|8866	|Vivacom							|Bulgaria			|1315|
|51167	|Contabo GmbH						|Germany			|967|
|237	|Merit Network Inc.					|United States		|219|
|4837	|CNCGROUP China169 Backbone			|China				|211|
|36866	|JTL								|Kenya				|197|
|4134	|Chinanet							|China				|185|
|4766	|Korea Telecom						|Republic of Korea	|155|
|8452	|TE Data							|Egypt				|141|
|7552	|Viettel Corporation				|Vietnam			|130|


<h4>Distribution By IP Reputation</h4>

|IP Reputation	|Count            
|:--------------|:----|
|Missing		|47174|
|known attacker	|14323|
|bad reputation	|123  |
|mass scanner	|70   |


<h4>Distribution Attack By Protocoll</h4>        

|Destination Port | Protocoll	  |Count            
|:----------------|:--------------|:-----|
|23				|telnet			  |342|
|22				|ssh			  |22|
|1433			|mssqld			  |40849|
|81				|httpd			  |39|
|3306			|mysqld			  |17|
|21				|ftpd			  |8|
|1883			|mqttd			  |6|
|27017			|mongod			  |5|
|1723			|pptpd			  |1|
|49834			|TftpServerHandler|1|
|55852			|TftpServerHandler|1|
|59217			|TftpServerHandler|1|
 
 
 <h4>Attack By Username</h4> 
 
|USER	| Count   |
|:------|:--------|
|sa|40714|
|root|152|
|admin|79|
||61|
|default|46|
|guest|7|
|support|6|
|mother|5|
|service|4|
|supervisor|4|
|tech|3|
|user|3|
|888888|2|
|Admin|2|
|pi|2|
|ubnt|2|
|666666|1|
|Administrator|1|
|administrator|1|
|bin|1|
|dameon|1|
|ftp|1|
|telnetadmin|1|
|vstarcam2015|1|

