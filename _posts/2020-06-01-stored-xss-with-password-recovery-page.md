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
excerpt: 'EN \| Stored XSS with Password Recovery Page'
---

In April of this year, I found a Stored Xss vulnerability at University of Utwente. However, I later realized that there was a vendor of
the vulnerable system, and I contacted them. Then they fixed this vuln. and rewarded me with a $$$ bounty. Also this was my first bounty.
I don't say the company that produced the system because they want to remain confidential.

### Recon
I discovered XSS with a simple payload execution in the "First Name" input. But I thought this vuln was a Self XSS.
Because all pages were private for every user (except for one page).
