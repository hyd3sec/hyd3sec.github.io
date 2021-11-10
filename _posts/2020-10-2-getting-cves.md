---
layout: post
title: A Simple Guide to Getting CVEs
categories: [Security Research]
tags: [cve, security research, publishing]
description: A step-by-step guide on how to obtain CVEs.
---

### Co-authored with Bobby Cooke (@0xboku)

So you found a vulnerability and you want to get a CVE? SWEET!

Make sure that the vulnerability doesn’t already exist. That’d be lame if you went through all this work only to find it’s already out there… but still kudos to you for finding it! The only place you REALLY need to check is the MITRE database, but you should also check google, github, etc.

Contact the vendor/product owner and disclose the issue. Now if they have a bug bounty program that you’re involved with then unfortunately their disclosure policies may prevent you from disclosing it at all. Here’s the important part… take screenshots, save emails, do whatever to make sure that you document that you attempted to contact the application owner. This is where the clock starts ticking.

When contacting the vendor, aim for coordinated disclosure. In an ideal situation, you will release the vulnerability details after the vendor has been able to release a patch. With a responsive and cooperative vendor, MITRE has great documentation on how to progress your CVE to disclosure that can be found here: https://cve.mitre.org/CVEIDsAndHowToGetThem.pdf . However, for many reasons, the vendor will ghost you. If this is the case (and it typically is) this is what we do…

Disclosure is a gray area with no defined rules, but most people wait 30, 60, 90, or even up to 120 days after notifying/attempting to notify the vendor before disclosing. While you are waiting, go to the MITRE website and fill out the CVE request form. This process is going to be done on a case-by-case basis (ex. if the company/owner is a CVE Numbering Authority, also known as a CNA).

If you don’t see them in the CNA list, fill out this form: https://cveform.mitre.org/. This has taken us roughly 30 days on average, so we like to submit this once we find the vulnerability. Once you get a CVE ID (they will notify you by email), you’ll notice that it’s in a RESERVED state. This means that your CVE has been accepted by MITRE but has not been published yet.

Now while you’re waiting, it’s generally a good idea to keep trying to contact the application owner/developer at least every 30 days. Once you have waited however long you decide to/whatever the application owner and you agree upon, it’s time to publish! This is the best way that we have found to accomplish this:

    Send POC/exploit to PacketStorm Security/CX Security. A good format for the header is what Exploit-DB shows here: https://www.exploit-db.com/submit. Make sure that you include the RESERVED CVE-ID that you got from MITRE when you submit to these two websites.

    Once the exploits are published, send the links to MITRE by replying to the email that they sent you with a link to the published POC/Exploit.

    MITRE typically has a quick turn-around for this (1 day or so). Sometimes they email you with an update, sometimes they don’t. Best thing to do is to check the original CVE Link they sent and see if it changed from RESERVED and shows the details of the CVE.

    CONGRATS! YOU’VE GOT A PUBLISHED CVE!!!

    If you so choose, you can now try to send your exploit/POC to exploit-db. They typically won’t respond with an update on whether they decide to publish or not, but if not, try and try again!



EDIT: My friend Valerio had an issue where MITRE wasn’t being responsive. He had this addition:

If Mitre doesn’t respond to your email after months, it’s enough to open a new request not as a “CVE Request” but as “other”, specifying you are waiting for such a long time… after doing this, they replied to him after 24 hours with CVE IDs. Thanks Valerio!

Happy Hunting!

Resources: https://cve.mitre.org/CVEIDsAndHowToGetThem.pdf
