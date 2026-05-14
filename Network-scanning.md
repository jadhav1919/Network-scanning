# Scanning Networks

# 1. What is Network Scanning?

Before scanning:
- Attacker first performs **Footprinting / Reconnaissance**
- Then starts **Scanning**

Scanning means:

> Collecting more detailed information about the target network or system.

The attacker tries to find:
- Live systems
- Open ports
- Running services
- Operating systems
- Vulnerabilities


# 2. Objectives of Network Scanning

Main goals:

| Objective | Purpose |
|---|---|
| Find live hosts | Identify active systems |
| Find open ports | Discover entry points |
| Identify services | Know what is running |
| Detect OS | Understand target environment |
| Find vulnerabilities | Discover weaknesses |
| Map network | Understand structure |

---

# 3. Types of Scanning

## A. Port Scanning

Checks:
- Which ports are open
- Which services are listening

### Example

| Port | Service |
|---|---|
| 80 | HTTP |
| 443 | HTTPS |
| 22 | SSH |

### Why Important?

Open ports can become entry points for attackers.

---

## B. Network Scanning

Finds:
- Active hosts
- IP addresses

### Goal

Know:
- Which systems are alive on the network

---

## C. Vulnerability Scanning


Searches for:
- Security weaknesses
- Misconfigurations
- Outdated software

### Example

- Old Apache server
- Weak SMB configuration
- Unpatched Windows system

---

# 4. Important Scanning Concepts

# TCP Communication Flags

TCP uses flags to control communication.

Important flags:

| Flag | Full Form | Purpose |
|---|---|---|
| SYN | Synchronize | Start connection |
| ACK | Acknowledgement | Confirm packet received |
| FIN | Finish | End connection |
| RST | Reset | Abort connection |
| PSH | Push | Send data immediately |
| URG | Urgent | Urgent processing |

---

# 5. TCP Three-Way Handshake

This is very important.

Connection establishment process:

```text
Client → SYN → Server
Client ← SYN-ACK ← Server
Client → ACK → Server
```

After this:
Connection established

![TCP Three-Way Handshake](images/tcp-three-way-handshake.png)

# 6. TCP Connection Termination

Closing connection:

```text
Client → FIN → Server
Client ← ACK ← Server
Server → FIN → Client
Server ← ACK ← Client
```

Connection closed.

![TCP Connection Termination](images/tcp-connection-termination.png)

# 7. Scanning Tools

# A. Nmap

## What is Nmap?

Nmap = Network Mapper

Used for:
- Host discovery
- Port scanning
- Service detection
- OS detection

---

## Basic Syntax

```bash
nmap <target-ip>
```

Example:

```bash
nmap 192.168.1.1
```

# B. Hping3

## What is Hping3?

Hping3 is an advanced:
- Network scanning tool
- Packet crafting tool
- Firewall testing tool

It allows attackers or security testers to:
- Create custom TCP/IP packets
- Test firewall rules
- Scan ports
- Perform OS fingerprinting
- Analyze network behavior

---

# Features of Hping3

- ICMP Scanning
- TCP Scanning
- UDP Scanning
- SYN/ACK Scanning
- Firewall Testing
- Packet Crafting
- Traceroute Mode
- OS Fingerprinting
- Idle Host Scanning

---

# Basic Syntax

```bash
hping3 <options> <target-ip>
```

Example:

```bash
hping3 10.0.0.25
```

---

# Important Hping3 Commands

---

# 1. ICMP Ping Scan

## Command

```bash
hping3 -1 10.0.0.25
```

---

## Breakdown

| Part | Meaning |
|---|---|
| `hping3` | Tool name |
| `-1` | ICMP mode |
| `10.0.0.25` | Target IP |

---

## Purpose

Used to:
- Check whether host is alive
- Perform ping sweep
- Test connectivity

---

## How It Works

Hping3 sends:
- ICMP Echo Request packets

Target replies with:
- ICMP Echo Reply packets

Similar to:
```bash
ping 10.0.0.25
```

---

# 2. ACK Scan

## Command

```bash
hping3 -A 10.0.0.25 -p 80
```

---

## Breakdown

| Part | Meaning |
|---|---|
| `-A` | Set ACK flag |
| `-p 80` | Target port 80 |

---

## Purpose

Used for:
- Firewall detection
- Checking filtering rules

---

## How It Works

Hping3 sends:
- TCP packets with ACK flag set

### If:
- Firewall allows → Response received
- Firewall blocks → No response

---

## Important Note

ACK scan usually does:
- NOT determine open ports directly
- It mainly checks firewall behavior

---

# 3. UDP Scan

## Command

```bash
hping3 -2 10.0.0.25 -p 80
```

---

## Breakdown

| Part | Meaning |
|---|---|
| `-2` | UDP mode |
| `-p 80` | Target port |

---

## Purpose

Used to:
- Scan UDP ports
- Discover UDP services

---

## How It Works

Hping3 sends:
- UDP packets

### Responses:
| Response | Meaning |
|---|---|
| ICMP Port Unreachable | Port closed |
| No response | Port may be open |

---

# 4. SYN Scan

## Command

```bash
hping3 -8 50-60 -S 10.0.0.25
```

---

## Breakdown

| Part | Meaning |
|---|---|
| `-8` | Enable scan mode |
| `50-60` | Scan ports 50 to 60 |
| `-S` | Set SYN flag |
| `10.0.0.25` | Target IP |

---

## Purpose

Used to:
- Find open TCP ports
- Perform stealth scanning

---

## How It Works

Hping3 sends:
- SYN packets
- To ports 50 → 60

### Responses

| Response | Meaning |
|---|---|
| SYN-ACK | Port open |
| RST | Port closed |

---

## Similar Nmap Command

```bash
nmap -sS 10.0.0.25
```

---

# 5. FIN / PSH / URG Scan

## Command

```bash
hping3 -F -P -U 10.0.0.25 -p 80
```

---

## Breakdown

| Option | Meaning |
|---|---|
| `-F` | FIN flag |
| `-P` | PSH flag |
| `-U` | URG flag |
| `-p 80` | Target port |

---

## Purpose

Used for:
- Advanced stealth scanning
- Firewall evasion
- Detecting filtered ports

---

## How It Works

Hping3 sends:
- Special TCP packets with FIN, PSH, URG flags

### Responses

| Response | Meaning |
|---|---|
| No response | Port may be open |
| RST response | Port closed |

---

# 6. Collect Initial Sequence Numbers

## Command

```bash
hping3 192.168.1.103 -Q -p 139
```

---

## Purpose

Used to:
- Collect TCP sequence numbers
- Analyze TCP behavior

---

# 7. Firewall Timestamp Scan

## Command

```bash
hping3 -S 72.14.207.99 -p 80 --tcp-timestamp
```

---

## Purpose

Used to:
- Analyze firewall behavior
- Check TCP timestamp handling
- Estimate uptime

---

# 8. Scan Entire Subnet

## Command

```bash
hping3 -1 10.0.1.x --rand-dest -I eth0
```

---

## Purpose

Used to:
- Discover live hosts in subnet
- Perform random destination scanning

---

# 9. Intercept HTTP Traffic

## Command

```bash
hping3 -9 HTTP -I eth0
```

---

## Purpose

Used to:
- Capture packets containing HTTP signatures
- Monitor HTTP traffic

---

# 10. SYN Flood Attack

## Command

```bash
hping3 -S 192.168.1.1 -a 192.168.1.254 -p 22 --flood
```

---

## Purpose

Used to:
- Generate massive SYN packets
- Perform DoS attack simulation

---

# C. Metasploit

## What is Metasploit?

Penetration testing framework.

Used for:
- Exploitation
- Vulnerability scanning
- Payload generation
- Post exploitation

---

## Example Use

Search scanner modules:

```bash
search portscan
```

---
![Metasploit Port Scanning Modules](images/metasploit-portscan-modules.png)

# D. NetScanTools Pro

GUI-based scanning tool.

Features:
- Port scanning
- DNS lookup
- Host discovery
- Network mapping

---
![NetScanTools Pro ARP Scan](images/netscantools-arp-scan.png)
