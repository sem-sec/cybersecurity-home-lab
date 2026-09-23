# Networking Fundamentals

## Topics Covered

### IP Addressing and Interfaces
- Loopback interface (127.0.0.1) vs real network interfaces
- Reading interface output with `ip a`

### DNS
- How domain names resolve to IP addresses
- Used `nslookup` and `dig` to query DNS records
- Understood local DNS resolver (127.0.0.53) vs upstream DNS servers
- Learned about non-authoritative vs authoritative answers

### Ports and Protocols
- Purpose of ports (0–65535) and common port numbers (22 SSH, 53 DNS, 80 HTTP, 443 HTTPS, 3389 RDP)
- TCP: connection-based, reliable, uses a three-way handshake (SYN, SYN-ACK, ACK)
- UDP: connectionless, faster, no delivery guarantee
- Practical relevance: TCP handshake abuse in SYN flood (DoS) attacks

### Subnetting
- CIDR notation and subnet math: host bits = 32 − prefix, total addresses = 2^(host bits), usable = total − 2
- Solved subnetting problems by hand (e.g., 192.168.1.0/27 → usable range 192.168.1.1–192.168.1.30, network address 192.168.1.0, broadcast address 192.168.1.31)

### OSI Model
- All seven layers and their real-world equivalents (Physical through Application)
- Connected practical tools already used (ping, traceroute, ss) to their corresponding OSI layers
- MAC addresses and the OUI (vendor identifier) portion of a MAC address

### Firewalls
- Used UFW (Uncomplicated Firewall) on Ubuntu to enable firewall rules
- Practiced the "default deny, explicit allow" security principle

### HTTP vs HTTPS
- Plaintext (HTTP, port 80) vs encrypted (HTTPS, port 443) traffic
- Inspected raw HTTP response headers using `curl -I`
- Identified CDN/security infrastructure (Cloudflare) from response headers as a basic reconnaissance technique

## Tools Used
`ip a`, `ping`, `nslookup`, `dig`, `traceroute`, `ss -tuln`, `curl -I`, `ufw`
