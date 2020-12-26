---
title: 'EN \| Account Takeover via Web Cache Poisoning based Reflected XSS'
date: 2020-12-26
permalink: /posts/acc-takeover-web-cache-xss/
tags:
  - web cache poisoning
  - account takeover
  - web cache poisoning to account takeover
  - reflected xss to account takeover
  - reflected xss
  - hack
  - bugbounty
  - write-up
  - poc
excerpt: 'Firstly, it's nice to publish my last write-up this year. In June of this year, I found a Reflected XSS vulnerability in a video-game company. Then, I realized that this server is caching the weak parameter's value. In this way, I incresead the...'
---

<img src="https://lutfumertceylan.com.tr/images/web-cache.png"><br>

Firstly, it's nice to publish my last write-up this year. In June of this year, I found a Reflected XSS vulnerability in a video-game company. Then, I realized that this server is caching the weak parameter's value.
In this way, I incresead the probability of triggering this vulnerability and escalated to Account Takeover weakness.
Later, I reported the vulnerability and they fixed this vulnerability. Also, they rewarded me with a €€€ bounty. I can't say the company, because I have no permission to disclose them.

### Recon


I discovered a Reflected XSS with a basic payload execution (`1</script><svg/onload=confirm("document.cookie")>`) in the “language” input. I thought this vuln was a normal Reflected XSS. As usual, the vulnerability was triggered when going to
the vulnerable URL and user session was stolen with a suitable payload. Because, the session cookie did not have any `httponly` or `secure` flags.

For those who don't know what httponly and secure flag is:
> `HttpOnly:` An HttpOnly Cookie is a tag added to a browser cookie that prevents client-side scripts from accessing data. [from CookiePro]
> `secure:` When a secure flag is used, then the cookie will only be sent over HTTPS, which is HTTP over SSL/TLS. When this is the case, the attacker eavesdropping on the communication channel from the browser to the server will not be able to read the cookie (HTTPS provides authentication, data integrity and confidentiality). [from infosecinstitute]

### Impact Escalation with Web Cache Poisoning!
But then, I saw that each page also contains `language` parameter. And I realized that the value of this parameter is put in the web cache. So this means:
> Even if the vulnerability was triggered just once, the payload would be embedded in all pages of this site. <br>

Actually, this does not cached entire page like standart Web Cache Poisoning weaknesses, only the part where the payload is embedded is cached. But of course, this is still a web cache poisoning. This scheme prepared by
Detectify may be useful for you.

<img src="https://blog.detectify.com/wp-content/uploads/2020/07/web_cache_poisoning.png"><br>

### And a simple Account Takeover

As we mentioned at the beginning, there was no `httponly` and `secure` flag or a `Content-Security-Policy (CSP)` that can block payload on the site.

<img src="/images/xsscac.png"><br>

So admittedly, the system was already very weak. 

### Attack scenario with Web Cache Poisoning
With Web Cache Poisoing, we can create a simple attack scenario. For example, if the victim sends a request in the background from an external page to the vulnerable URL in several ways(like embedding the vulnerable url in a picture),
The payload is cached in the web, and the payload is triggered each time the victim goes the target site.

I reported the vulnerability, and they agreed that it should be fixed.

### The end and results :

17 June 2020 - Report sent<br>
18 June 2020 - Confirmed<br>
24 June 2020 - I was awarded a €€€ bounty<br>
