# Port and Service Discovery

# What is Port and Service Discovery?

After identifying live hosts, the next step is:
- Discovering open ports
- Identifying running services

Attackers use port scanning to:
- Find entry points
- Detect vulnerable services
- Gather information about target systems
  
Administrators use it to:
- Verify security policies
- Identify unnecessary open ports
- Improve network security


# Objectives of Port Scanning

- Discover open ports
- Identify running services
- Detect service versions
- Find vulnerable services
- Determine operating systems
- Map network structure


# Common Ports and Services

| Name | Port/Protocol | Description |
|---|---|---|
| echo | 7/tcp, udp | Echo service |
| discard | 9/tcp, udp | Sink null |
| systat | 11/tcp | Active users |
| daytime | 13/tcp, udp | Daytime service |
| netstat | 15/tcp, udp | Network status |
| qotd | 17/tcp, udp | Quote of the day |
| chargen | 19/tcp, udp | Character generator |
| ftp-data | 20/tcp | FTP data transfer |
| ftp | 21/tcp | FTP command |
| ssh | 22/tcp | Secure Shell |
| telnet | 23/tcp | Remote login |
| smtp | 25/tcp | Email server |
| time | 37/tcp, udp | Time server |
| rlp | 39/tcp, udp | Resource location |
| domain | 53/tcp, udp | DNS |
| sql*net | 66/tcp, udp | Oracle SQL*Net |
| bootps | 67/udp | Bootp server |
| bootpc | 68/udp | Bootp client |
| tftp | 69/udp | Trivial File Transfer |
| gopher | 70/tcp | Gopher server |
| finger | 79/tcp | Finger |
| www-http | 80/tcp, udp | WWW |
| www-https | 80/tcp | Secure WWW |
| kerberos | 88/tcp, udp | Kerberos |
| pop2 | 109/tcp | Post Office V2 |
| pop3 | 110/tcp | Post Office V3 |
| sunrpc | 111/tcp, udp | RPC Portmapper |
| auth/ident | 113/tcp, udp | Authentication service |
| audionews | 114/tcp, udp | Audio News Multicast |
| nntp | 119/tcp | Network News Transfer |
| ntp | 123/udp | Network Time Protocol |
| netbios-ns | 137/tcp, udp | NetBIOS Name Service |
| netbios-dgm | 138/tcp, udp | NetBIOS Datagram Service |
| netbios-ssn | 139/tcp, udp | NetBIOS Session Service |
| imap | 143/tcp, udp | IMAP |
| sql-net | 150/tcp, udp | SQL-NET |
| sqlsrv | 156/tcp, udp | SQL Service |
| snmp | 161/tcp | SNMP |
| snmp-trap | 162/tcp, udp | SNMP Trap |
| cmip-man | 163/tcp, udp | CMIP Manager |
| cmip-agent | 164/tcp, udp | CMIP Agent |
| irc | 194/tcp, udp | IRC |
| at-rtmp | 201/tcp, udp | AppleTalk Routing |
| at-nbp | 202/tcp, udp | AppleTalk Name Binding |
| at-3 | 203/tcp, udp | AppleTalk |
| at-echo | 204/tcp, udp | AppleTalk Echo |
| at-5 | 205/tcp, udp | AppleTalk |
| at-zis | 206/tcp, udp | AppleTalk Zone Info |
| at-7 | 207/tcp, udp | AppleTalk |
| at-8 | 208/tcp, udp | AppleTalk |
| ipx | 213/tcp, udp | Novell IPX |
| imap3 | 220/tcp | IMAP v3 |
| aurp | 387/tcp, udp | AppleTalk Routing |
| netware-ip | 396/tcp, udp | Netware over IP |
| rmt | 411/tcp, udp | Remote mt |
| kerberos-ds | 445/tcp, udp | Microsoft DS |
| isakmp | 500/udp | ISAKMP/IKE |
| fcp | 510/tcp | First Class Server |
| exec | 512/tcp | BSD rexecd |
| comsat/biff | 512/udp | Mail notification |
| login | 513/tcp | BSD rlogin |
| who | 513/udp | BSD rwho |
| shell | 514/tcp | BSD rsh |
| syslog | 514/udp | BSD syslog |
| printer | 515/tcp, udp | BSD printer |
| talk | 517/tcp, udp | BSD talk |
| ntalk | 518/udp | SunOS talk |
| netnews | 532/tcp, udp | Readnews |
| uucp | 540/tcp, udp | UUCP |
| klogin | 543/tcp, udp | Kerberos Login |
| kshell | 544/tcp, udp | Kerberos Shell |
| ekshell | 545/tcp | Encrypted Shell |
| pserver | 600/tcp | PC Board Server |
| mount | 635/udp | NFS Mount |
| pcnfs | 640/udp | DOS Authentication |
| bwnfs | 650/udp | BW-NFS |
| flexlm | 744/tcp, udp | License Manager |
| kerberos-adm | 749/tcp | Kerberos Admin |
| kerberos | 750/tcp, udp | Kerberos |
| kerberos_master | 751/tcp, udp | Kerberos Master |
| krb_prop | 754/tcp | Kerberos Propagation |
| applix | 999/udp | Applixware |
| socks | 1080/tcp, udp | SOCKS Proxy |
| kpop | 1109/tcp | POP with Kerberos |
| ms-sql-s | 1433/tcp, udp | Microsoft SQL Server |
| ms-sql-m | 1434/tcp, udp | Microsoft SQL Monitor |
| pptp | 1723/tcp, udp | PPTP |
| nfs | 2049/tcp, udp | Network File System |
| eklogin | 2105/tcp | Kerberos Login |
| rkinit | 2108/tcp | Remote kinit |
| kx | 2111/tcp | X over Kerberos |
| kauth | 2120/tcp | Remote kauth |
| lyskom | 4894/tcp | LysKOM |
| sip | 5060/tcp | Session Initiation Protocol |
| sip | 5060/udp | Session Initiation Protocol |
| x11 | 6000-6063/tcp, udp | X Window System |
| irc | 6667/tcp | Internet Relay Chat |


# Categories of Port Scanning Techniques

## TCP Scanning
- TCP Connect/Full-Open Scan
- Stealth/Half-Open Scan
- Inverse TCP Flag Scan
  - Xmas Scan
  - FIN Scan
  - NULL Scan
  - Maimon Scan
- ACK Flag Probe Scan
  - TTL-Based Scan
  - Window-Based Scan
- IDLE/IPID Header Scan


## UDP Scanning
- UDP Scan


## SCTP Scanning
- SCTP INIT Scan
- SCTP COOKIE/ECHO Scan


## SSDP Scanning
- SSDP and List Scanning


## IPv6 Scanning
- IPv6 Scanning


# 1. TCP Connect / Full-Open Scan

## What is TCP Connect Scan?

TCP Connect Scan:
- Completes full TCP three-way handshake
- Checks whether port is open


## Working Process

### Open Port && Closed Port

![TCP Connect Scan Working](images/tcpw.png)

## Nmap Command

```bash
nmap -sT 10.10.1.11
```
![TCP Connect Scan Zenmap Output](images/tcp-connect-zenmap.png)
---

## Advantages

- Reliable
- Accurate

---

## Disadvantages

- Easily detected
- Generates logs
- Not stealthy

---

# 2. Stealth Scan (Half-Open Scan)

## What is Stealth Scan?

Stealth Scan:
- Sends SYN packet
- Does not complete full connection

Also called:
- SYN Scan
- Half-open Scan

---

## Working Process

### Open Port && Closed Port

![Stealth Scan Working](images/sw.png)


## Nmap Command

```bash
nmap -sS 10.10.1.11
```
![Stealth Scan Zenmap](images/stealth-scan-zenmap.png)
---

## Advantages

- Fast
- Stealthy
- Bypasses some logging systems

---

# 3. Inverse TCP Flag Scan

## What is Inverse TCP Flag Scan?

Uses packets with:
- FIN
- URG
- PSH
- or no flags

---

## Responses

| Response | Meaning |
|---|---|
| No response | Port open |
| RST/ACK | Port closed |

---

## Types

- FIN Scan
- NULL Scan
- Xmas Scan

![Inverse TCP Flag Scan](images/iw.png)


## Advantages

- Highly stealthy
- Can bypass IDS/firewalls

---

## Disadvantages

- Mostly effective on UNIX systems
- Not reliable on Windows

---

# 4. Xmas Scan

## What is Xmas Scan?

Sends packets with:
- FIN
- URG
- PSH flags enabled

---

## Working Process && Closed Port


![Xmas Scan Working](images/xmas.png)


## Nmap Command

```bash
nmap -sX 10.10.1.11
```
![Xmas Scan Zenmap](images/xmas-scan-zenmap.png)
---

## Advantages

- Avoids some IDS systems
- No full TCP handshake

---

## Disadvantages

- UNIX-only effectiveness
- Fails on many Windows systems

---

# 5. FIN Scan

## What is FIN Scan?

Sends:
- FIN flag only

---

## Responses

| Response | Meaning |
|---|---|
| No response | Port open |
| RST | Port closed |

---

## Nmap Command

```bash
nmap -sF 10.10.1.11
```

---

# 6. NULL Scan

## What is NULL Scan?

Sends packets:
- With no TCP flags

---

## Responses

| Response | Meaning |
|---|---|
| No response | Port open |
| RST | Port closed |

---

## Nmap Command

```bash
nmap -sN 10.10.1.11
```

---

# 7. TCP Maimon Scan

## What is Maimon Scan?

Similar to:
- FIN Scan
- NULL Scan
- Xmas Scan

Uses:
- FIN/ACK packets

---

## Responses

| Response | Meaning |
|---|---|
| No response | Open/Filtered |
| RST | Closed |
| ICMP unreachable | Filtered |

---

![TCP Maimon Scan](images/mw.png)


## Nmap Command

```bash
nmap -sM 10.10.1.11
```
![TCP Maimon Scan Zenmap](images/maimon-scan-zenmap.png)
---

# 8. ACK Flag Probe Scan

## What is ACK Scan?

Sends:
- ACK packets

Used for:
- Firewall detection
- Filtering analysis

---

## Working Process




## Nmap Command

```bash
nmap -sA 10.10.1.11
```
![ACK Scan Zenmap](images/ack-scan-zenmap.png)

---

# 9. TTL-Based ACK Scan

## What is TTL Scan?

Analyzes:
- TTL value of RST packets

---

## Rule

| TTL Value | Meaning |
|---|---|
| TTL < 64 | Port open |
| TTL > 64 | Port closed |

---
![ACK Probe Scan Working](images/ack.png)

---

# 10. Window-Based ACK Scan

## What is Window Scan?

Analyzes:
- TCP window size

---

## Rule

| Window Value | Meaning |
|---|---|
| Non-zero | Port open |
| Zero | Port closed |

---

# Screenshot Section

```markdown
![Window Based ACK Scan](images/wa1.png)
```

---

# 11. Firewall Detection using ACK Scan

## Stateful Firewall Present

```text
Attacker → ACK Probe → Target
No Response
```

✅ Firewall Present

---

## No Firewall

```text
Attacker → ACK Probe → Target
RST Response
```

❌ No Firewall

---

# Screenshot Section

```markdown
![Firewall Detection ACK Scan](images/firewall-detection-ack.png)
```

---

# 12. IDLE/IPID Header Scan

## What is IDLE Scan?

Advanced stealth scanning technique using:
- Spoofed IP address
- Zombie system

---

# Important Terms

| Term | Meaning |
|---|---|
| Zombie | Idle host used for scanning |
| IPID | IP Identification value |

---

# IDLE Scan Steps

## Step 1 — Probe Zombie

```text
Attacker → SYN/ACK → Zombie
Zombie → RST(IPID=X) → Attacker
```
![Idle Scan Step 1](images/s1.png)
---

## Step 2 — Spoof SYN Packet

```text
Attacker → SYN(spoofed zombie IP) → Target
```

### If Port Open

```text
Target → SYN/ACK → Zombie
Zombie → RST → Target
```

Zombie IPID increases.
![Idle Scan Step 2](images/s2.png)
---

## Step 3 — Probe Zombie Again

```text
Attacker → SYN/ACK → Zombie
Zombie → RST(IPID=X+2) → Attacker
```

If IPID increased:
✅ Port is Open

---
![Idle Scan Step 3](images/s3.png)

![Idle Scan Nmap Output](images/idle-scan-nmap.png)
```

---

## Nmap Command

```bash
nmap -sI zombie_ip target_ip
```

Example:

```bash
nmap -sI 10.10.1.19 10.10.1.11
```

---

## Advantages

- Extremely stealthy
- Hides attacker identity

---

## Disadvantages

- Complex setup
- Requires idle zombie system

---

# 13. UDP Scan

## What is UDP Scan?

UDP scanning:
- Uses UDP instead of TCP
- No three-way handshake

---

## Working Process

### Open Port

```text
Attacker → UDP Packet → Target
No Response
```

Port may be Open
![UDP Scan Working](images/udp.png)
---

### Closed Port

```text
Attacker → UDP Packet → Target
ICMP Port Unreachable ← Target
```

 Port Closed

---

# Screenshot Section

```markdown

```

```markdown
![UDP Scan Zenmap](images/udp-scan-zenmap.png)
```

---

## Nmap Command

```bash
nmap -sU 10.10.1.22
```

---

## Advantages

- Useful for discovering UDP services
- Can bypass some TCP filters

---

## Disadvantages

- Slow scanning
- Difficult to identify open ports

---

# 14. SCTP INIT Scan

## What is SCTP?

SCTP:
- Stream Control Transmission Protocol

Uses:
- Four-way handshake

---

## SCTP Four-Way Handshake

```text
Client → INIT → Server
Client ← INIT-ACK ← Server
Client → COOKIE-ECHO → Server
Client ← COOKIE-ACK ← Server
```

---

![SCTP Four Way Handshake](images/sctp.png)


```markdown
![SCTP INIT Scan Working](images/sctp-init-working.png)
```

```markdown
![SCTP INIT Zenmap](images/sctp-init-zenmap.png)
```

---

## Working Process

### Open Port

```text
Attacker → INIT Chunk → Target
Attacker ← INIT-ACK ← Target
```

✅ Port Open

---

### Closed Port

```text
Attacker → INIT Chunk → Target
Attacker ← ABORT Chunk ← Target
```

❌ Port Closed

---

## Nmap Command

```bash
nmap -sY 10.10.1.11
```

---

## Advantages

- Distinguishes open/closed/filtered ports
- More stealthy than full SCTP connection

---

# 15. SCTP COOKIE-ECHO Scan

## What is SCTP COOKIE-ECHO Scan?

Uses:
- COOKIE-ECHO chunk

More stealthy than:
- SCTP INIT scan

---

## Working Process

### Open Port && Closed Port

![SCTP COOKIE ECHO Working](images/sc.png)

```markdown
![SCTP COOKIE ECHO Zenmap](images/sctp-cookie-zenmap.png)
```

---

## Nmap Command

```bash
nmap -sZ 10.10.1.11
```

---

## Advantages

- Stealthy
- Harder to detect

---

## Disadvantages

- Cannot clearly distinguish open and filtered ports

---

# 16. SSDP Scan

## What is SSDP?

SSDP:
- Simple Service Discovery Protocol

Used in:
- UPnP devices

---

## Purpose

Used for:
- Discovering network devices
- Finding UPnP-enabled systems
- Detecting vulnerable IoT devices

---

## Metasploit Command

```bash
use auxiliary/scanner/upnp/ssdp_msearch
```

---

# Screenshot Section

```markdown
![SSDP Scan Metasploit](images/ssdp-scan-metasploit.png)
```

---

# 17. List Scan

## What is List Scan?

List Scan:
- Displays target information
- Does not actively scan hosts

---

## Nmap Command

```bash
nmap -sL 10.10.1.11
```

---

# Screenshot Section

```markdown
![List Scan Zenmap](images/list-scan-zenmap.png)
```

---

## Advantages

- Fast
- Useful for validating targets

---

# 18. IPv6 Scan

## What is IPv6 Scanning?

Scans:
- IPv6 hosts and services

IPv6 uses:
- 128-bit addressing

---

## Challenges

- Huge address space
- Difficult host discovery
- Traditional ping sweeps less effective

---

## Nmap Command

```bash
nmap -6 scanme.nmap.org
```

---

# Screenshot Section

```markdown
![IPv6 Scan Nmap](images/ipv6-scan-nmap.png)
```

---

