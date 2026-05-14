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

Advanced packet crafting and scanning tool.

Used for:
- ICMP scan
- SYN scan
- ACK scan
- Firewall testing
- Packet crafting

---

# Important Hping3 Commands

## 1. ICMP Ping Scan

```bash
hping3 -1 10.0.0.25
```

### Meaning

- `-1` → ICMP mode

Similar to ping.

---

## 2. ACK Scan

```bash
hping3 -A 10.0.0.25 -p 80
```

### Meaning

- `-A` → ACK flag
- `-p 80` → Target port 80

Used for:
- Firewall detection

---

## 3. UDP Scan

```bash
hping3 -2 10.0.0.25 -p 80
```

### Meaning

- `-2` → UDP mode

---

## 4. SYN Scan

```bash
hping3 -8 50-60 -S 10.0.0.25
```

### Meaning

- `-8` → Enable scan mode
- `50-60` → Port range
- `-S` → SYN flag

---

## 5. FIN/PSH/URG Scan

```bash
hping3 -F -P -U 10.0.0.25 -p 80
```

### Meaning

Uses:
- FIN
- PSH
- URG flags

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

# D. NetScanTools Pro

GUI-based scanning tool.

Features:
- Port scanning
- DNS lookup
- Host discovery
- Network mapping

---
