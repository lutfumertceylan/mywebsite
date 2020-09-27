---
title: 'EN \| Clickjacking to Account Takeover via Drag&Drop'
date: 2020-09-27
permalink: /posts/clickjacking-acc-takeover-drag-drop/
tags:
  - clickjacking
  - account takeover
  - clickjacking to account takeover
  - drag & drop
  - Bug Bounty
  - hack
  - bugbounty
  - write-up
  - poc
excerpt: 'In August of this year, I found a Clickjacking vulnerability in a dutch company. Later I realized that this vulnerability could be upgraded to Account Takeover. Then, I coded a PoC template with CSS and reported the vulnerability. And they fixed...'
---

<img src="https://portswigger.net/web-security/images/clickjacking-infographic.svg"><br>

In August of this year, I found a Clickjacking vulnerability in a dutch company. Later I realized that this vulnerability could be upgraded to Account Takeover. Then,
I coded a PoC template with CSS and reported the vulnerability. And they fixed this vulnerability and rewarded me with a €€€ bounty. I don't say the company, because they
want to remain confidential.

### Recon
I was reviewing the responses by sending requests to the system. When I looked at response header, I saw that the `X-Frame-Options` attribute was not set. This was causing 
the Clickjacking vulnerability. 


### Impact Escalation
I saw there was a control panel page for users. Also, due to the system, when the e-mail address was changed, user accounts could be taken over.<br>

<img src="/images/codeclick.png"><br>

> Template Source: <a href="https://pastebin.ubuntu.com/p/WKtVKBBd4F/">https://pastebin.ubuntu.com/p/WKtVKBBd4F/</a> 

I coded a template using the drag&drop feature with CSS and HTML.<br>

<video width="500" controls>
  <source src="/images/click-acc.mp4" type="video/mp4">
</video>

### Reported
I can hear what you think. Yes, Since the drag & drop feature is used, the impact of the vulnerability is reduced. However, it is still a weakness that is likely to
cause serious damage. I reported the vulnerability, and we agreed with the company that it should be fixed.

### The end :

7 August 2020 - Report sent<br>
8 August 2020 - Confirmed<br>
11 August 2020 - I was awarded a €€€ bounty<br>
