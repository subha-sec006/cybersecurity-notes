# IP Address

## What is an IP address?
An IP address is a unique identifier assigned to a device on a network. It works like a home address: data needs it to know where to go. Example: 192.168.1.5

## IPv4 vs IPv6
- IPv4: 32-bit, written as four numbers from 0 to 255 (e.g., 192.168.1.1)
- IPv6: 128-bit, written in hexadecimal (e.g., 2001:db8::1)
- IPv6 was created because IPv4 addresses are running out.

## Public vs Private IP
- Public IP: visible on the internet, assigned by your ISP.
- Private IP: used inside a local network (home, office) and not reachable directly from the internet.
- Private ranges:
  - 10.0.0.0 to 10.255.255.255
  - 172.16.0.0 to 172.31.255.255
  - 192.168.0.0 to 192.168.255.255

## Static vs Dynamic IP
- Static: fixed, does not change. Used for servers.
- Dynamic: assigned automatically by DHCP and can change over time.

## Special IP addresses
- 127.0.0.1: localhost (your own computer)
- 0.0.0.0: "any address" or unspecified
- 255.255.255.255: broadcast to all devices on the local network

## Subnet mask basics
- A subnet mask splits an IP into the network part and the host part.
- 255.255.255.0 is the same as /24, which means the first 24 bits are the network.
- A /24 network has 254 usable host addresses.

## Useful commands
- Windows: `ipconfig`
- Linux: `ip a`
- Test connectivity: `ping 8.8.8.8`

## Why it matters in cybersecurity
- Analysts check logs to find suspicious source IPs.
- Firewalls allow or block traffic by IP.
- Attackers often scan IP ranges to find open ports.
- Tools like AbuseIPDB and VirusTotal help check if an IP is malicious.
