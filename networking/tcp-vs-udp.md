# TCP vs UDP

## What are TCP and UDP?
Both are transport layer protocols. They decide how data travels between two devices after the IP address is known.

## TCP (Transmission Control Protocol)
- Connection-oriented: sets up a connection first using a 3-way handshake.
- Reliable: lost packets are re-sent.
- Ordered: data arrives in the correct order.
- Slower because of the extra checking.
- Used for: web (HTTP/HTTPS), email (SMTP), file transfer (FTP), SSH.

## TCP 3-way handshake
1. SYN: client says "I want to connect."
2. SYN-ACK: server says "OK, I am ready."
3. ACK: client says "Confirmed." Connection is open.

## UDP (User Datagram Protocol)
- Connectionless: sends data without setting up a connection.
- Not reliable: lost packets are not re-sent.
- No ordering guarantee.
- Faster and lightweight.
- Used for: DNS, video calls, online games, live streaming.

## Quick comparison
| Feature | TCP | UDP |
|---|---|---|
| Connection | Yes (handshake) | No |
| Reliability | High | Low |
| Speed | Slower | Faster |
| Example | HTTPS, SSH | DNS, video call |

## Useful command
- netstat -an (Windows): shows open connections with TCP/UDP and their states

## Why it matters in cybersecurity
- SYN flood attack: attacker sends many SYN packets and never completes the handshake, so the server runs out of resources.
- Port scanners (like Nmap) use TCP SYN scans to find open ports.
- UDP floods and DNS amplification are common DDoS methods.
- Analysts check protocol and port in logs to judge if traffic is normal.

## My hands-on example
Command: `netstat -an`

Sample lines from my output (shortened):

```
TCP  0.0.0.0:445          0.0.0.0:0            LISTENING
TCP  10.x.x.x:57099       140.82.112.26:443    ESTABLISHED
TCP  10.x.x.x:57100       104.18.18.203:443    TIME_WAIT
UDP  0.0.0.0:123          *:*
```

### What I learned
- LISTENING: my computer is waiting for connections on that port (e.g., 445 for SMB).
- ESTABLISHED: an active connection, such as my browser talking to a website over port 443 (HTTPS).
- TIME_WAIT / CLOSE_WAIT: connections that are closing.
- UDP lines have no State column because UDP is connectionless.
- Most outgoing connections use port 443 (HTTPS), so it is the most common port.
- Port 123 (UDP) is NTP, used for time sync.
