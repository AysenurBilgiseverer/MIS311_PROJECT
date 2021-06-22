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

Website [ink] (ttps://bilginerbelgelendirme.com/)

***According to scan result, ZAP found a total of 12 alarms on this website. 
Eight of these alarms risk are low and their confidence are medium.
One of these alarms risk is medium and its confidence is medium.
The remaining 3 are due to some coding errors, etc., which have no risk that their risk define as informational and their confidence are low.***

#### Some Test Results
1. **Alert name: X-Frame-Options Header Not Set**

Risk:Medium

Confidence:Medium 

Decription: X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks.

Solution: Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY. ALLOW-FROM allows specific websites to frame the web page in supported web browsers).

2. **Alert name: Cookie No HttpOnly Flag**

Risk:Low

Confidence:Medium 

Decription: A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.

Solution: Ensure that the HttpOnly flag is set for all cookies.

3. **Alert name: Cookie Without SameSite Attribute**

Risk:Low

Confidence:Medium 

Decription: A cookie has been set without the SameSite attribute, which means that the cookie can be sent as a result of a 'cross-site' request. The SameSite attribute is an effective counter measure to cross-site request forgery, cross-site script inclusion, and timing attacks.

Solution: Ensure that the SameSite attribute is set to either 'lax' or ideally 'strict' for all cookies.

References: https://tools.ietf.org/html/draft-ietf-httpbis-cookie-same-site

4. **Alert name: Incomplete or No Cache-control and Pragma HTTP Header Set**

Risk:Low

Confidence:Medium 

Decription: The cache-control and pragma HTTP header have not been set properly or are missing allowing the browser and proxies to cache content.

Solution: Whenever possible ensure the cache-control HTTP header is set with no-cache, no-store, must-revalidate; and that the pragma HTTP header is set with no-cache.

5. **Alert name: Charset Mismatch**

Risk:Informational

Confidence:Low

Decription: This check identifies responses where the HTTP Content-Type header declares a charset different from the charset defined by the body of the HTML or XML. When there's a charset mismatch between the HTTP header and content body Web browsers can be forced into an undesirable content-sniffing mode to determine the content's correct character set.
An attacker could manipulate content on the page to be interpreted in an encoding of their choice. For example, if an attacker can control content at the beginning of the page, they could inject script using UTF-7 encoded text and manipulate some browsers into interpreting that text.

Solution: Force UTF-8 for all text content in both the HTTP header and meta tags in HTML or encoding declarations in XML.





