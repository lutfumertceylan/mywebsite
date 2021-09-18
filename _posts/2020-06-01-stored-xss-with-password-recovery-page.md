---
title: 'EN \| Stored XSS with Password Recovery Page'
date: 2020-06-01
permalink: /posts/stored-xss-with-password-recovery-page/
tags:
  - stored xss
  - xss in password recovery
  - Bug Bounty
  - hack
  - bugbounty
  - write-up
  - poc
excerpt: 'In April of this year, I found a Stored Xss vulnerability at University of Utwente. However, I later realized that there was a vendor of the vulnerable system, and I contacted them. Then they fixed this vuln. and rewarded me with a $$$ bounty. Also this was my first bounty...'
---

<img src="/images/cross-site-scripting.svg"><br>

In April of this year, I found a Stored Xss vulnerability at University of Utwente. However, I later realized that there was a vendor of
the vulnerable system, and I contacted them. Then they fixed this vuln. and rewarded me with a $$$ bounty. Also this was my first bounty.
I don't say the company that produced the system because they want to remain confidential.

### Recon
I discovered XSS with a simple payload execution in the "First Name" input. But I thought this vuln was a Self XSS.
Because all pages were private for every user (except for one page). Then I saw that the password recovery page also contains user First Name value.


### First Try
I type a payload in the "first_name" input<br>
<img src="/images/payl.png">  

but the system always encodes the payloads on Profile Page.<br>
<img src="/images/payl2.png">

Profile Page was not public anyway. Not bad luck!

### Catch You!!
I believed XSS was no longer possible. But there is one last place, "Password Recovery Page", Moreover, it reflects the user's "first_name" value to the page.

I just created the page with the request to create a Password Recovery Page. The system not encode the payload on this page. So payload was executed!

### The end :

9 April 2020 - Report sent<br>
10 April 2020 - Scenario requested<br>
13 April 2020 - Report's scenario sent<br>
14 April 2020 - I was awarded a $$$ bounty<br>
