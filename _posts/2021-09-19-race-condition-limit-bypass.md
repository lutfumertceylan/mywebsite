---
title: 'EN \| Race Condition to Users Limit Bypass in Add User Function'
date: 2021-09-19
permalink: /posts/race-condition-limit-bypass1/
header_extra: <meta property="og:image" content="https://lutfumertceylan.com.tr/images/race-condition0.png" />
tags:
  - race condition
  - limit bypass
  - Bug Bounty
  - hack
  - bugbounty
  - write-up
  - poc
excerpt: "In September of last year, I found a Race Condition vulnerability at an Online Services company located in the Netherlands. They had a private Zerocopter program and that's why I was doing bug hunting based on web applications, on their systems. And I reported the..."
---

<img src="/images/race.png"><br>
<hr><br>
In September of last year, I found a Race Condition vulnerability at an Online Services company located in the Netherlands. They had a private Zerocopter
program and that's why I was doing bug hunting based on web applications, on their systems. And I reported the vulnerability to them. Then, they fixed this vulnerability and rewarded me with a €€€ bounty.


## Firstly, what is a Race Condition?

<blockquote>
<b>What Is a Race Condition?</b><br>
In any computing system, there are some tasks that need to be completed in a specific order. For example, before allowing someone to log in, a security system first receives their username and password and then checks it against a database before allowing access. Attackers can exploit this fact by interfering with processes to access secure areas and content in what's known as a race condition attack.
</blockquote>
<blockquote>
<b>What Is a Race Condition Vulnerability?</b><br>
Race condition attacks (also called Time of Check to Time of Use, or TOCTTOU attacks) take advantage of the need that computing systems must execute some tasks in a specific sequence. In any such sequence, there is a small period of time when the system has carried out the first task but not started on the second. If this period is long enough or the attacker is lucky and knowledgeable, a race condition vulnerability exists where an attacker can trick the system into carrying out unauthorized actions in addition to its normal processes.<br>
  There are two main ways this attack is carried out:
 </blockquote>
<blockquote>
<b>Interference by an untrusted process</b> - The attacker inserts a piece of code in between the steps of a secure process.
  <br><br>
<b>Interference by a trusted process</b> - The attacker exploits two different processes that share some state in common.
<p align="right"><i>-Veracode</i></p>
</blockquote>

## Recon

When I was doing my pre-research normally for system recognition, I had already determined that they did not have a Rate Limit and I had reported it before. Of course, as you know, we cannot talk
about the existence of Race Condition vulnerability without No Rate Limit. Because these two are related vulnerabilities.
<br><br>
The Race Condition vulnerability can exist thanks to a base formed by the
No Rate Limit vulnerability. Later, I realized that this vulnerability is not only in a single function, but in every function. And I researched for the riskiest place to amplify the impact.

<hr>

## There is something..

I was trying to prove the existence of a Race Condition vulnerability in a function with no impact.
For this I use Turbo Intruder, which is a plugin of Burp Suite. If you want to get it, you can find it on the BApp Store.<br>
<img src="/images/turbo-int.jpg"><br>

I was also detecting the vulnerability with this code snippet.<br>
<img src="/images/race-script-dark.jpg"><br>

You can go to this tweet to access this code snippet: [a Python Snippet to try Race Condition weakness in Turbo Intruder](https://twitter.com/lutfumertceylan/status/1320980232015384576/)
<br><br>
And yes, this system had a Race Condition vulnerability.
<img src="/images/race-done.jpg"><br>
<hr>

## Eureka!

I had already grasped how the system works in pre-research. A premium membership(worth ~500€) was required to add multiple users to the test group. So a free membership could only add 1 user to the group.
I found the Add User function and executed the code snippet here with the Turbo Intruder.<br>
<img src="/images/race-panel.png"><br>

And yeah! Like other functions, the Add User function also had a Race Condition vulnerability. And I was able to add as many users as I wanted to my test group. So I was able to do things on a free account that only a premium account can do.
<br><br>
As you can see in the screenshot, my limit to add **1** user as a free membership has decreased to **-22**. So we broke the limit counter.

## The end :

13 September 2020 - Report sent<br>
15 September 2020 - Confirmed by triager<br>
22 September 2020 - Internal team denied impact of report<br>
25 September 2020 - Zerocopter discuss with Internal team<br>
05 October 2020 - Internal team also accept the impact of the vulnerability<br>
05 October 2020 - I was awarded a €€€ bounty
