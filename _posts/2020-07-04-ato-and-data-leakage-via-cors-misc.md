---
title: 'EN \| Account Takeover and Sensitive Data Leakage via CORS Misconfiguration'
date: 2020-07-04
permalink: /posts/ato-and-data-leakage-via-cors-misc/
tags:
  - cors misconfiguration
  - account takeover
  - sensitive data leak
  - Bug Bounty
  - hack
  - bugbounty
  - write-up
  - poc
excerpt: "EN /| Account Takeover and Sensitive Data Leakage via CORS Misconfiguration"
---

<img src="https://portswigger.net/web-security/images/attack-on-cors.svg"><br>

In June of this year, I found a CORS Misconfiguration vulnerability in a datacenter company. The system was very simple, a PUT command sent to the API Server
both changed the account email and showed all the data of the account in JSON format as Response. Then, I reported this weakness and the company rewarded me 
with a $$$ bounty. Also, I would like to thank <a href="https://twitter.com/bugraeskici">Bugra Eskici</a> , who helped me a lot to detect this vulnerability.

### Recon
I was reviewing the responses by sending requests to the system. When I looked at request header, I saw that the "Origin" attribute was defined.
The vulnerable site was defined in the "Origin" attribute as a value, and this value was also defined in the "Access-Control-Allow-Origin" attribute in the Response.
Also, the "Access-Control-Allow-Credentials" value was "true".

### Is it vulnerable?
I write evil.com as the value to Origin. And Bingo! The response status was "200 OK" and evil.com was also included in the Access-Control-Allow-Origin attribute.<br>

<img src="/images/corsheader.png"><br>

That is, there was a CORS Misconfiguration vulnerability.

### Double Shot!!
I can change the account email with a simple PUT request. Moreover, the server was showing the sensitive data of the account as Response. Then, I have created a simple
script for both changing email and stealing sensitive data.

You can find the script I created in my tweet:
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">A script you can use for Sensitive Data Leakage via CORS Misconfiguration 🕵️🧙‍♂️<br><br>Source Code: <a href="https://t.co/TroWuo34cJ">https://t.co/TroWuo34cJ</a><a href="https://twitter.com/hashtag/bugbountytips?src=hash&amp;ref_src=twsrc%5Etfw">#bugbountytips</a> <a href="https://twitter.com/hashtag/bugbountytip?src=hash&amp;ref_src=twsrc%5Etfw">#bugbountytip</a> <a href="https://twitter.com/hashtag/bugbounty?src=hash&amp;ref_src=twsrc%5Etfw">#bugbounty</a> <a href="https://twitter.com/hashtag/cybersecurity?src=hash&amp;ref_src=twsrc%5Etfw">#cybersecurity</a> <a href="https://twitter.com/hashtag/infosec?src=hash&amp;ref_src=twsrc%5Etfw">#infosec</a> <a href="https://twitter.com/hashtag/ethicalhacking?src=hash&amp;ref_src=twsrc%5Etfw">#ethicalhacking</a> <a href="https://t.co/e0hId2BKmG">pic.twitter.com/e0hId2BKmG</a></p>&mdash; Lütfü Mert Ceylan (@lutfumertceylan) <a href="https://twitter.com/lutfumertceylan/status/1274829687177515011?ref_src=twsrc%5Etfw">June 21, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script><br>

With the script, I changed the e-mail address by sending a PUT request. (Account Takeover)
<img src="/images/putreqcors.jpg"><br>

Then, I sent the Response containing sensitive data to a request-bin service with this script.
<img src="/images/respcors.jpg"><br>

And, sensitive data sent the attacker's site.
<img src="/images/sensdatacors.jpg"><br>

So I was able to both change the e-mail address of the victim account and steal sensitive data. Both vulnerabilities were caused by CORS Misconfiguration.
As I have explained, it is possible to exploit these vulnerabilities with a simple script.

### The end :

10 June 2020 - Report sent<br>
10 June 2020 - Confirmed <br>
11 June 2020 - I awarded a $$$ bounty<br>
