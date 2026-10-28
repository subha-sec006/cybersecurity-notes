# DNS (Domain Name System)

## What is DNS?
DNS converts a domain name (google.com) into an IP address (142.250.x.x). Humans remember names easily, but computers communicate using IP addresses. It works like a phone book for the internet.

## How a DNS lookup works
1. You type google.com in the browser.
2. The browser checks its own cache.
3. If not found, the request goes to a DNS resolver (usually your ISP or 8.8.8.8).
4. The resolver asks the root server, then the TLD server (.com), then the authoritative server.
5. The IP address is returned and your browser connects to it.

## Common DNS record types
- A: domain to IPv4 address
- AAAA: domain to IPv6 address
- CNAME: alias of another domain
- MX: mail server for the domain
- TXT: text data (used for SPF, DKIM, verification)
- NS: name servers of the domain

## Useful commands
- nslookup google.com
- dig google.com (Linux)
- ipconfig /flushdns (Windows, clears DNS cache)
## My nslookup example
Command: nslookup google.com

Result:
- DNS server used: 10.66.154.228 (a private IP, my network's resolver)
- IPv6 address: 2404:6800:4007:83a::200e
- IPv4 addresses: 142.250.146.101, 142.250.146.139, 142.250.146.100, and more

What I learned:
- "Non-authoritative answer" means the reply came from my resolver's cache, not directly from Google's own DNS server.
- google.com returned both IPv6 and IPv4 addresses.
- One domain can have many IP addresses. This is used for load balancing.
- The DNS server's IP (10.x.x.x) is a private IP, which matches what I learned in ip-address.md.

## Why it matters in cybersecurity
- DNS spoofing/poisoning: attacker gives a fake IP for a real domain.
- Phishing sites use look-alike domains (g00gle.com).
- Malware uses DNS to contact its command-and-control server.
- DNS logs help SOC analysts spot suspicious domains.
