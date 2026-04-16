# CompTIA Network+ (N10-009) Study Guide
### Synthesized from Star V Learning Centers Course Materials

---

## PART 1: NETWORKING FUNDAMENTALS (24%)

### What Is a Network?

Anytime you connect two or more systems together and they communicate, you have a network. Networks share resources like files and printers.

### Network Types

| Type | Meaning | Scope |
|------|---------|-------|
| PAN | Personal Area Network | Bluetooth range (~10m) |
| BAN | Body Area Network | Wearable devices on a person |
| LAN | Local Area Network | Single building or office |
| CAN | Campus Area Network | Multiple buildings on a campus |
| MAN | Metropolitan Area Network | City-wide |
| WAN | Wide Area Network | Geographically dispersed, connects LANs |
| SAN | Storage Area Network | Dedicated high-speed storage network |
| WLAN | Wireless LAN | Wireless version of a LAN |

### Network Architecture

**Peer-to-Peer:** Devices connect directly to each other. Each device manages its own security and resources. Simple but doesn't scale.

**Client/Server:** Clients request resources from centralized servers. The internet itself is a massive client/server network. Scales well, centralized management.

### The OSI Model (7 Layers)

The OSI (Open Systems Interconnection) model is a standard way to describe network communication as a series of layers. **This is the most tested concept on the exam.**

| Layer | Name | What It Does | PDU | Key Devices/Protocols |
|-------|------|-------------|-----|----------------------|
| 7 | Application | User-facing protocols | Data | HTTP, FTP, SMTP, DNS, DHCP |
| 6 | Presentation | Encryption, compression, formatting | Data | SSL/TLS, JPEG, ASCII |
| 5 | Session | Opens, manages, closes connections | Data | NetBIOS, SQL sessions |
| 4 | Transport | Reliable delivery, port numbers | Segment (TCP) / Datagram (UDP) | TCP, UDP |
| 3 | Network | IP addressing, routing | Packet | IP, ICMP, Routers |
| 2 | Data Link | MAC addressing, switching | Frame | Ethernet, Switches, ARP |
| 1 | Physical | Cables, signals, connectors | Bits | Hubs, cables, NICs |

**Mnemonic (bottom to top):** Please Do Not Throw Sausage Pizza Away

**Encapsulation:** As data moves down the layers, each layer adds a header. Layer 4 creates segments, Layer 3 wraps them in packets, Layer 2 wraps those in frames, Layer 1 converts to bits. The reverse (de-encapsulation) happens on the receiving end.

### TCP vs. UDP

| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | Connection-oriented | Connectionless |
| Reliability | Reliable, sequenced | Unreliable, unsequenced |
| Speed | Slower (overhead) | Faster (low overhead) |
| Acknowledgements | Yes | No |
| Flow Control | Windowing | None |
| Use Cases | HTTP, FTP, email, file transfer | DNS queries, VoIP, streaming, DHCP |

**TCP Three-Way Handshake:** SYN → SYN-ACK → ACK

### TCP Header Fields (Key Ones)

- **Source/Destination Port** — identifies the application (16-bit each)
- **Sequence Number** — for reassembly (32-bit)
- **Acknowledgment Number** — confirms data received (32-bit)
- **Window Size** — how many bytes can be accepted at once (flow control)
- **Checksum** — error checking

### Communication Types

- **Simplex** — one way only (like a TV broadcast)
- **Half Duplex** — one way at a time (like a walkie-talkie). Used by WLANs and hubs.
- **Full Duplex** — both directions simultaneously. Used by switches.

### Contention Methods

- **CSMA/CD** (Collision Detection) — used by wired Ethernet. Devices detect collisions and retry after random delay.
- **CSMA/CA** (Collision Avoidance) — used by wireless (802.11). Devices announce how long they need the medium before transmitting.

### Broadcast and Collision Domains

- **Broadcast Domain** — all devices that receive a broadcast. Only routers separate broadcast domains.
- **Collision Domain** — a network segment where collisions can occur. Switches create separate collision domains per port. Hubs do NOT.

---

## PART 2: CABLING & CONNECTORS

### Copper Media

**Coaxial Cable:** Uses BNC connectors. ThinNet (RG-58) is the legacy standard. Plenum-rated cable is fire-resistant for use in air ducts.

**Twisted Pair Cable:**
- **UTP** (Unshielded Twisted Pair) — no shielding, 4 pairs, inexpensive, most common
- **STP** (Shielded Twisted Pair) — shielding around conductors, more expensive, reduces interference

**Twisted Pair Categories:**

| Category | Speed | Max Distance |
|----------|-------|-------------|
| Cat 5 | 100 Mbps | 100m |
| Cat 5e | 1 Gbps | 100m |
| Cat 6 | 10 Gbps (55m) / 1 Gbps (100m) | 100m |
| Cat 6a | 10 Gbps | 100m |

**Connectors:**
- **RJ-45** — Ethernet (8 pins)
- **RJ-11** — Phone lines (6 pins)

### Fiber Optic Cable

| Type | Core Size | Use | Jacket Color |
|------|-----------|-----|-------------|
| Single-Mode (SMF) | 9 µm | Long distance (up to 10+ km) | Yellow |
| Multi-Mode (MMF) | 50 or 62.5 µm | Short distance (up to 550m) | Orange or Aqua |

**Fiber Connectors:**

| Connector | Description |
|-----------|-------------|
| LC | Small, RJ-45-type latch, most common in data centers |
| SC | Square/box-shaped, push-pull, common in duplex configs |
| ST | Round, bayonet twist-lock, common in patch panels |
| MTRJ | RJ-45 sized, snap-to-lock, connects two multimode fibers |

**Fiber Polish Types:**
- **PC** (Physical Contact) — ~-40 dB back reflection, most applications
- **UPC** (Ultra Physical Contact) — ~-55 dB, digital CATV and telephony
- **APC** (Angled Physical Contact) — ~-70 dB, 8-degree angle, CATV and analog

**Transceivers:**
- **SFP** (Small Form-factor Pluggable) — converts electrical to optical
- **SFP+** — supports 10 Gbps
- **QSFP** — Quad SFP, four channels, supports 10 Gbps

### Wiring Standards

- **T568A** and **T568B** — define the order of wire colors in an RJ-45 connector
- **T568B** is most common in the US (starts Orange-white, Orange)
- **Straight-through cable** — same standard on both ends (T568B to T568B). Connects different device types.
- **Crossover cable** — different standards on each end (T568A to T568B). Connects like devices.

### Ethernet Standards

| Standard | Speed | Medium | Max Distance |
|----------|-------|--------|-------------|
| 100Base-TX | 100 Mbps | Cat 5 UTP | 100m |
| 100Base-FX | 100 Mbps | MMF | 412m |
| 1000Base-T | 1 Gbps | Cat 5 UTP | 100m |
| 1000Base-SX | 1 Gbps | MMF | 220-550m |
| 1000Base-LX | 1 Gbps | SMF | 3-10 km |
| 10GBase-T | 10 Gbps | Cat 6a UTP | 100m |
| 10GBase-SR | 10 Gbps | MMF | 2-300m |
| 10GBase-LR | 10 Gbps | SMF | 2m-10 km |
| 10GBase-ER | 10 Gbps | SMF | 2m-40 km |

### Cable Properties to Know

- **Attenuation** — signal loss over distance
- **Crosstalk** — interference between wire pairs (near-end NEXT, far-end FEXT)
- **Interference** — EMI from external sources
- **Shorts** — wires touching that shouldn't be
- **Open** — broken wire, no continuity

---

## PART 3: NETWORKING DEVICES

| Device | OSI Layer | Function |
|--------|-----------|----------|
| Hub | 1 (Physical) | Repeats signal to all ports, shared collision domain |
| Switch | 2 (Data Link) | Forwards frames using MAC addresses, separate collision domains per port |
| Router | 3 (Network) | Routes packets between networks using IP addresses, separates broadcast domains |
| Multilayer Switch | 2-3 | Switches and routes (Layer 3 switch) |
| Firewall | 3-4 (or 7 for NGFW) | Filters traffic based on rules |
| WAP | 1-2 | Provides wireless access to a wired network |
| Load Balancer | 4-7 | Distributes traffic across multiple servers |
| Proxy Server | 7 | Intermediary between clients and the internet, caching and filtering |
| IDS | 3-7 | Monitors and alerts on threats |
| IPS | 3-7 | Monitors and blocks threats |
| VPN Concentrator | 3 | Terminates VPN tunnels |
| Media Converter | 1 | Converts between media types (fiber to Ethernet) |

### DNS (Domain Name System)

Resolves domain names to IP addresses. Uses port 53 (TCP and UDP).

**Key DNS concepts:**
- **FQDN** — Fully Qualified Domain Name (e.g., mail.google.com)
- **DNSSEC** — adds cryptographic signatures to verify DNS data authenticity
- **DoH** (DNS over HTTPS) — encrypts DNS queries over HTTPS
- **DoT** (DNS over TLS) — encrypts DNS queries over TLS

### DHCP (Dynamic Host Configuration Protocol)

Automatically assigns IP configuration. Ports 67 (server) / 68 (client).

**DORA Process:** Discover → Offer → Request → Acknowledge

**DHCP assigns:** IP address, subnet mask, default gateway, DNS servers, domain name

**DHCP Relay** — router forwards DHCP requests to a server on a different subnet

**IPAM** (IP Address Management) — software to manage both DNS and DHCP

---

## PART 4: IP ADDRESSING

### IPv4 Basics

- 32-bit address in dotted decimal notation (e.g., 192.168.1.1)
- Four octets (8 bits each)
- Has a network portion and a host portion

### IP Address Classes

| Class | Range | Default Mask | Purpose |
|-------|-------|-------------|---------|
| A | 1-126 | /8 (255.0.0.0) | Large networks |
| B | 128-191 | /16 (255.255.0.0) | Medium networks |
| C | 192-223 | /24 (255.255.255.0) | Small networks |
| D | 224-239 | — | Multicast |
| E | 240-255 | — | Experimental |

**Note:** 127.x.x.x is reserved for loopback (127.0.0.1)

### Private IP Ranges (RFC 1918)

| Class | Range |
|-------|-------|
| A | 10.0.0.0 – 10.255.255.255 |
| B | 172.16.0.0 – 172.31.255.255 |
| C | 192.168.0.0 – 192.168.255.255 |

**APIPA:** 169.254.0.0 – 169.254.255.255 (self-assigned when DHCP fails)

### Message Types

- **Unicast** — one-to-one
- **Broadcast** — one-to-all (NOT used in IPv6)
- **Multicast** — one-to-many (specific group)
- **Anycast** — one-to-nearest-of-many

### IPv6

- 128-bit address in hexadecimal notation (8 groups of 4 hex digits)
- Allows for 18 quintillion hosts per subnet
- **Shortening rules:**
  - Rule 1: Omit leading zeros (01ab → 1ab)
  - Rule 2: Replace one contiguous group of all-zero hextets with :: (can only use once)
- **Link-local:** fe80:: (auto-configured, not routable)
- **Global Unicast (GUA):** routable on the internet
- **SLAAC:** Stateless Address Autoconfiguration — devices configure their own IPv6 address from router advertisements

### NAT (Network Address Translation)

Translates private IPs to public IPs for internet access.

| Type | Description |
|------|-------------|
| Static NAT (SNAT) | One-to-one mapping (one private to one public) |
| Dynamic NAT (DNAT) | Maps from a pool of public addresses |
| PAT (Port Address Translation) | Many-to-one using port numbers — most common |

---

## PART 5: SUBNETTING

### Why Subnet?

- Reduce broadcast traffic
- Optimize network performance
- Simplify management
- Implement security between segments

### Subnetting Table (from /24)

| CIDR | Subnet Mask | Subnets | Usable Hosts |
|------|-------------|---------|-------------|
| /24 | 255.255.255.0 | 1 | 254 |
| /25 | 255.255.255.128 | 2 | 126 |
| /26 | 255.255.255.192 | 4 | 62 |
| /27 | 255.255.255.224 | 8 | 30 |
| /28 | 255.255.255.240 | 16 | 14 |
| /29 | 255.255.255.248 | 32 | 6 |
| /30 | 255.255.255.252 | 64 | 2 |

**Key formula:** 2^n = subnets (n = bits borrowed). Always subtract 2 from total addresses for usable hosts (network address + broadcast address).

**Magic Number Method:** Subtract the last non-zero octet of the subnet mask from 256 to get the subnet increment.
- /25: 256 - 128 = 128 (subnets at 0, 128)
- /26: 256 - 192 = 64 (subnets at 0, 64, 128, 192)
- /27: 256 - 224 = 32 (subnets at 0, 32, 64, 96, 128, 160, 192, 224)

---

## PART 6: ROUTING

### Routing Basics

Routing is the process of moving packets from one network to another using routing tables.

- **Static Routes** — manually configured by admin. Good for small networks. More secure.
- **Dynamic Routes** — learned automatically via routing protocols. Adapts to changes. Uses CPU/memory.

### Routing Protocols

| Protocol | Type | Metric | Max Hops | AD | Notes |
|----------|------|--------|----------|-----|-------|
| RIP | Distance vector | Hop count | 15 | 120 | Simple, slow convergence |
| OSPF | Link state | Cost (bandwidth) | None | 110 | Open standard, enterprise choice |
| EIGRP | Hybrid | Bandwidth + delay | 255 | 90 | Cisco proprietary, fast convergence |
| BGP | Path vector | AS path | — | 20 (external) | Routes between ISPs on the internet |

### Administrative Distance (AD)

Lower AD = more trusted. If a router learns the same route from multiple sources, it uses the one with the lowest AD.

| Source | AD |
|--------|-----|
| Directly connected | 0 |
| Static route | 1 |
| EIGRP | 90 |
| OSPF | 110 |
| RIP | 120 |

### Routing Table Codes

- **C** — Directly connected
- **L** — Local interface
- **S** — Static route
- **O** — OSPF
- **D** — EIGRP
- **S*** — Default route (gateway of last resort = 0.0.0.0/0)

---

## PART 7: SWITCHING & VLANs

### Three Switch Functions at Layer 2

1. **Address Learning** — learns MAC addresses from source frames and stores them in the MAC address table
2. **Forward/Filter** — forwards frames only to the correct port based on the MAC table
3. **Loop Avoidance** — uses STP to prevent switching loops

### VLANs (Virtual LANs)

Segment a single physical switch into multiple logical broadcast domains. Devices in different VLANs cannot communicate without a router or Layer 3 switch (inter-VLAN routing).

### Trunk Ports

Carry traffic for multiple VLANs between switches using **802.1Q** tagging.

### Spanning Tree Protocol (STP) — IEEE 802.1D

Prevents switching loops by logically blocking redundant paths.

**STP Port States:**
- Blocking → Listening → Learning → Forwarding → Disabled

**Rapid STP (RSTP)** has faster convergence:
- Discarding → Learning → Forwarding

**Without STP:** Broadcast storms occur — endless loops of broadcast frames that overwhelm the network.

---

## PART 8: WIRELESS NETWORKING

### 802.11 Standards

| Standard | Wi-Fi Name | Frequency | Max Speed |
|----------|-----------|-----------|-----------|
| 802.11a | — | 5 GHz | 54 Mbps |
| 802.11b | — | 2.4 GHz | 11 Mbps |
| 802.11g | — | 2.4 GHz | 54 Mbps |
| 802.11n | Wi-Fi 4 | 2.4/5 GHz | 600 Mbps |
| 802.11ac | Wi-Fi 5 | 5 GHz | 1.3+ Gbps |
| 802.11ax | Wi-Fi 6/6E | 2.4/5/6 GHz | 9.6 Gbps |

### Key Wireless Concepts

- **2.4 GHz** — better range, slower speed, more interference, 3 non-overlapping channels (1, 6, 11)
- **5 GHz** — faster speed, shorter range, less interference, more channels
- **6 GHz** — Wi-Fi 6E only, least interference
- **Non-overlapping channels:** 1, 6, 11 on 2.4 GHz

### Wireless Security

| Protocol | Encryption | Notes |
|----------|-----------|-------|
| WEP | RC4 | Broken, never use |
| WPA | TKIP | Legacy, being phased out |
| WPA2 | AES-CCMP | Current standard |
| WPA3 | GCMP / SAE | Newest, most secure |

### Wireless Modes

- **Ad-Hoc (IBSS)** — devices communicate directly, no access point
- **Infrastructure (BSS)** — all traffic goes through an access point
- **Extended Service Set (ESS)** — multiple APs with same SSID for roaming (must overlap 10%+)

### Wireless Components

- **WAP** — Wireless Access Point
- **WNIC** — Wireless Network Interface Card
- **Antennas:** Omnidirectional (all directions) vs Directional/Yagi (focused beam)
- **Thick AP** — standalone, full OS, managed separately
- **Thin AP** — controller-based, controller and AP split duties
- **Guest Networks** — access without full authentication, pre-shared key
- **Captive Portals** — web page on first connection (airports, hotels)

### Wireless Troubleshooting

- **Signal Degradation causes:** distance, walls, interference, protocol limitations
- **Site Survey:** pre-deployment (verify AP placement) and post-deployment (confirm design)
- **Heat maps** — visual representation of wireless coverage

### IoT Technologies

- **Z-Wave** — mesh network for home automation
- **ANT+** — sensor data monitoring (heart rate, lighting)
- **Bluetooth** — short range, attacks include Bluejacking (unsolicited messages) and Bluesnarfing (unauthorized data access)
- **NFC** — Near Field Communication, contactless payments
- **RFID** — Radio Frequency Identification, asset tracking
- **IR** — Infrared

### Cellular Technologies

- **GSM** — uses SIM cards, FDMA/TDMA
- **CDMA** — unique code per call, spreads across spectrum

---

## PART 9: REMOTE ACCESS & VPNs

### VPN Types

- **Site-to-Site** — connects two office networks permanently
- **Client-to-Site** — remote user connects to corporate network via VPN client
- **Clientless VPN** — uses SSL/TLS in a web browser, no client software needed

### Full Tunnel vs Split Tunnel

- **Full Tunnel** — ALL traffic goes through the VPN tunnel (more secure)
- **Split Tunnel** — only corporate traffic goes through VPN, internet traffic goes direct (better performance)

### Remote Access Protocols

- **RDP** (port 3389) — Microsoft remote desktop, supports drive/printer redirection
- **RDP Gateway** — allows secure RDP access over SSL without a VPN
- **VNC** — open-source alternative to RDP, uses RFB protocol
- **SSH** (port 22) — encrypted command-line remote access
- **Telnet** (port 23) — unencrypted, insecure, replaced by SSH

---

## PART 10: NETWORK OPERATIONS

### Performance Monitoring

**Device/Chassis Metrics:**
- Temperature — overheating causes reboots, dust is a major cause
- CPU — should not exceed 85% processor time, interrupts should not exceed 15%

**Memory Metrics:**
- Committed bytes in use >80% = need more memory
- Available MB <5% = need more memory
- Pages/second >1000 = possible memory leak

**Network Metrics:**
- Bandwidth — NIC utilization >70% = interface saturated
- Output queue length >2 = NIC not keeping up
- Latency — consistent delay, measured in RTT (Round Trip Time)
- Jitter — variance in delay, affects VoIP/video

### Interface Statistics

- **Link State** — up/down status
- **Speed/Duplex** — must match on both ends (mismatch causes errors)
- **CRC Errors** — data corruption, usually bad cable
- **Giants/Runts** — oversized/undersized frames

### Documentation

- **Physical Network Diagram** — shows physical layout, cable runs, device locations
- **Logical Network Diagram** — shows IP addresses, VLANs, logical connections
- **Baselines** — normal performance metrics for comparison

### Policies & Standards

- **SLA** (Service Level Agreement) — defines expected uptime and performance
- **Change Management** — formal process for making changes
- **AUP** (Acceptable Use Policy) — defines what users can do on systems

### SNMP & Syslog

- **SNMP** (port 161) — monitors network devices using OIDs, collects data from agents
- **Syslog** (port 514) — sends log messages to a central server

---

## PART 11: HIGH AVAILABILITY & DISASTER RECOVERY

### Redundancy Concepts

- **NIC Teaming** — multiple physical NICs as one logical interface for fault tolerance
- **Switch Clustering** — managed as single entity using Cluster Management Protocol
- **FHRP** (First Hop Redundancy Protocol) — router redundancy, virtual IP used by standby router
  - **HSRP** — Cisco proprietary
  - **VRRP** — IEEE open standard

### HA Configurations

- **Active/Active** — both devices handle traffic (load balancing + availability)
- **Active/Passive** — standby takes over if primary fails (fault tolerance)
- **Multiple ISPs / Diverse Paths** — redundant internet connections

### Storage Redundancy

- **RAID 1** — mirroring (OS drives)
- **RAID 5** — striping with parity (data drives, minimum 3 drives)
- **RAID 6** — double parity (minimum 4 drives, can lose 2 drives)

### Disaster Recovery Sites

| Type | Description | Recovery Time |
|------|-------------|--------------|
| Hot Site | Fully operational, mirrors production | Minutes/hours |
| Warm Site | Infrastructure ready, no active equipment | Days |
| Cold Site | Just empty space | Weeks |
| Cloud Site | Virtual, provisioned through CSP | Variable |

### Key Metrics

- **MTTR** — Mean Time to Repair
- **MTBF** — Mean Time Between Failures
- **RPO** — Recovery Point Objective (max acceptable data loss)
- **RTO** — Recovery Time Objective (max acceptable downtime)

### Facility Support

- **UPS** — Uninterruptible Power Supply
- **PDU** — Power Distribution Unit
- **Generator** — long-term backup power
- **HVAC** — cooling
- **Fire Suppression:** Wet pipe (most common), dry pipe, preaction, deluge, clean agents (replace Halon: FM-200, water, argon)

---

## PART 12: CLOUD & DATA CENTER

### Cloud Deployment Models

- **Public Cloud** — multi-tenant, accessible to any customer (AWS, Azure, GCP)
- **Private Cloud** — provisioned for a single organization
- **Community Cloud** — shared by a specific group of organizations
- **Hybrid Cloud** — combination of public and private

### Cloud Service Models

| Model | You Manage | Provider Manages |
|-------|-----------|-----------------|
| IaaS | OS, apps, data | Hardware, networking, storage |
| PaaS | Apps, data | OS, hardware, networking |
| SaaS | Nothing (just use it) | Everything |

### Software-Defined Networking (SDN)

Network devices managed centrally from a controller, not individually.

- **Application Layer** — network apps (IDS/IPS, load balancers)
- **Control Layer** — management plane, processes configuration and monitoring
- **Infrastructure Layer** — forwarding plane, actual network hardware

### Data Center Locations

- **Branch Office** — closest to users
- **On-Premises** — separate data center with own staff
- **Co-Location** — provider builds data center, you lease rack space

### Infrastructure as Code (IaC)

Automates provisioning through scripted code instead of manual configuration. Benefits: reusability, speed, fewer configuration errors.

---

## PART 13: NETWORK SECURITY

### Security Devices

- **Firewall** — filters traffic based on rules. Placed between internet and internal network. DMZ sits between two firewalls.
- **NGFW** (Next-Gen Firewall) — operates at Layer 7, deep packet inspection
- **IDS** — monitors and alerts
- **IPS** — monitors and blocks
- **HIDS** — host-based IDS, installed on individual machines

### Authentication Protocols

| Protocol | Transport | Port | Use |
|----------|-----------|------|-----|
| RADIUS | UDP | 1812/1813 | Network access authentication |
| TACACS+ | TCP | 49 | Network device administration |
| Kerberos | TCP/UDP | 88 | Single sign-on in Active Directory |
| LDAP | TCP | 389 | Directory services queries |
| LDAPS | TCP | 636 | LDAP over SSL/TLS |

### 802.1X — Port-Based Network Access Control

Authenticates devices before granting network access. Uses a supplicant (client), authenticator (switch/AP), and authentication server (RADIUS).

### Common Attacks

- **DDoS** — floods target from many sources
- **ARP Spoofing** — fake ARP replies redirect traffic
- **DNS Poisoning** — corrupts DNS records
- **VLAN Hopping** — exploits trunk ports to jump VLANs
- **MAC Flooding** — overwhelms switch MAC table
- **On-Path Attack** — intercepts communication between two parties
- **Bluejacking** — unsolicited Bluetooth messages
- **Bluesnarfing** — unauthorized Bluetooth data access

---

## PART 14: TROUBLESHOOTING

### CompTIA Troubleshooting Methodology (7 Steps)

1. **Identify the problem** — question users, identify changes, check logs
2. **Establish a theory of probable cause** — question the obvious (port speed, duplex mismatch, wrong VLAN, incorrect IP, wrong gateway, wrong DNS, wrong subnet mask)
3. **Test the theory** — investigate to verify
4. **Establish a plan of action** — identify potential effects
5. **Implement the solution or escalate**
6. **Verify full system functionality** — implement preventive measures
7. **Document findings, actions, and outcomes**

### Command-Line Tools

| Command | Purpose |
|---------|---------|
| ping | Tests connectivity using ICMP |
| tracert / traceroute | Shows path to destination using TTL and ICMP |
| ipconfig / ifconfig | Shows network configuration |
| ipconfig /all | Shows full config including DNS and DHCP |
| ipconfig /release | Releases DHCP address |
| ipconfig /renew | Requests new DHCP address |
| ipconfig /flushdns | Clears DNS cache |
| arp -a | Shows IP-to-MAC mappings |
| nslookup | Queries DNS records |
| netstat | Shows active connections and ports |
| nmap | Scans for open ports |
| tcpdump | Captures packets (CLI) |
| Wireshark | Captures and analyzes packets (GUI) |
| pathping | Combines ping + tracert with packet loss stats |

### Troubleshooting Steps (from class)

1. Ping 127.0.0.1 (test TCP/IP stack)
2. Ping your own IP (test local NIC)
3. Ping default gateway (test local network)
4. Ping remote server (test full connectivity)

### Common Issues to Check

- Port speed/duplex mismatch
- Incorrect VLAN assignment
- Wrong IP address, gateway, DNS, or subnet mask
- Cable issues (crosstalk, attenuation, shorts, opens)
- Broadcast storms (no STP)
- MTU mismatch

### Network Analysis Tools

- **Wi-Fi Analyzer** — visualizes wireless networks, channels, signal strength
- **Protocol Analyzer** — captures raw packets (Wireshark, tcpdump)
- **Throughput Tester** — measures bandwidth and classifies traffic types
- **Port Scanner** — finds open TCP/UDP ports (nmap)
- **NetFlow Analyzer** — uses NetFlow data to view traffic patterns

---

## PART 15: PORTS REFERENCE

| Port | Protocol | TCP/UDP |
|------|----------|---------|
| 20 | FTP Data | TCP |
| 21 | FTP Control | TCP |
| 22 | SSH / SFTP | TCP |
| 23 | Telnet | TCP |
| 25 | SMTP | TCP |
| 53 | DNS | TCP/UDP |
| 67/68 | DHCP | UDP |
| 69 | TFTP | UDP |
| 80 | HTTP | TCP |
| 110 | POP3 | TCP |
| 123 | NTP | UDP |
| 137-139 | NetBIOS | TCP/UDP |
| 143 | IMAP | TCP |
| 161 | SNMP | UDP |
| 389 | LDAP | TCP |
| 443 | HTTPS | TCP |
| 445 | SMB | TCP |
| 465/587 | SMTPS | TCP |
| 514 | Syslog | UDP |
| 636 | LDAPS | TCP |
| 993 | IMAP over SSL | TCP |
| 995 | POP3 over SSL | TCP |
| 1433 | SQL Server | TCP |
| 1521 | SQLnet (Oracle) | TCP |
| 1720 | H.323 (Video) | TCP |
| 3306 | MySQL | TCP |
| 3389 | RDP | TCP |
| 5004/5005 | RTP (VoIP) | UDP/TCP |
| 5060/5061 | SIP (VoIP) | TCP/UDP |

---

## PART 16: MPLS & WAN TECHNOLOGIES

### MPLS (Multi-Protocol Label Switching)

One of the most popular WAN protocols. Uses labels (numbers) instead of IP addresses to forward data through the MPLS cloud. Each router assigns labels, creating logical connections between sites. Faster than traditional routing because routers don't need to do full IP lookups at every hop.

---

*Study tip: Use this guide as your reference backbone and supplement with the flashcard app for drilling. Focus on the OSI model, subnetting, and ports first — those three topics appear in every domain on the exam.*
