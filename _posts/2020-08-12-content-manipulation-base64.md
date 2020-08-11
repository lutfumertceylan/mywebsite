---
title: 'EN \| Alert-box Message Content Manipulation based Base64'
date: 2020-08-12
permalink: /posts/alertbox-manipulation-base64/
tags:
  - content manipulation
  - content spoofing
  - base64 paramater
  - Bug Bounty
  - hack
  - bugbounty
  - write-up
  - poc
excerpt: 'Alert-box Message Content Manipulation based Base64'
---

<img src="https://mk0resourcesinfm536w.kinstacdn.com/wp-content/uploads/ContentSpoofing08022013.jpg"><br>

In July of this year, I found a Content Spoofing vulnerability in a Bitcoin Exchange company. The system was very simple, a encrypted text in a 
GET parameter was decrypted and reflected on the homepage in an alertbox. I know it's very simple and its impact is <b>very low</b>. <u>In my philosophy, every finding
is worth reporting.</u> Then, I reported this weakness and the company rewarded me with a $$$ bounty.

### Recon

I was doing research on page of the website that do not require authentication, and I started researching the login page. While trying to login with some default credentials, 
I saw it execute "wrong username or password" warning on an GET parameter named "?e=". I saw the parameter's value is encrypted with Base64 and tried printing something else.
The website did not fail and reflected what I wrote on the screen as a warning.

### Mechanism

I placed the text in the picture below, which I encrypted with Base64, into the parameter. The system also executed this message.

<img src="/images/alertcontent.jpg"><br>

### Weakness is weakness...

I know that this vulnerability is simply and very low impact. Personally, I am careful to report every findings I find. 


### The end :

17 June 2020 - Report sent<br>
18 June 2020 - Confirmed <br>
27 June 2020 - I was awarded a $100 bounty<br>
