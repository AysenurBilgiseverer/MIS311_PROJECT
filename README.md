# MIS311_PROJECT

## PENETRATION TEST WITH OWASP-ZAP

### DESCRIPTION OF ZAP
ZED Attack Proxy (ZAP) is an OWASP project that allows to automatically investigate vulnerabilities of an existing website. It can be used as a useful part of a regular security test or integrated into a  index of CDs to provide ongoing checks for common security vulnerabilities. At the same time, using a tool like ZAP is a good addition to the toolbox as another tool to help ensure our systems are more secure. 

It is aimed to be used by beginners for penetration testing and professional penetration testing experts. Besides Automatic Scanners, ZAP provides A toolkit That lets users can find vulnerabilities manually. It has a plugin architecture and an online 'work area' that allows adding new or updated features. The GUI control panel is easy to use. It can also run in a daemon mode, which is then controlled via a rest API. 

#### Features
* It can be used as a proxy server and all of the packages on the network can be changed.
* Traditional and AJAX Web Browsers
* Automatic scanner
* Passive scanner
* Active Scanning
* Fuzzer
* WebSocket Support
* Script Languages
* Plug-n-hack support
* Easy to install and use.
* A lot of language support available.
* It can be improved because it is open source.
* Web and AJAX Spider property.
* Index has scanning support. 

**Penetration Test was applied on the website of Bilginer Certification Company.**

https://bilginerbelgelendirme.com/

#### Some Test Results
1. **Alert name: X-Frame-Options Header Not Set**

Risk:Medium

Confidence:Medium 

Decription: X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks.

Solution: Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY. ALLOW-FROM allows specific websites to frame the web page in supported web browsers).

