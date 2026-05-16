# Nmap
- Today we are going to see Nmap tool.
- It is very essential tool for network scanning in Penitration testing.
- We are going to see following parameters related with Nmap.

 ---

 ## 📌 What is Nmap?

**Nmap (Network Mapper)** is the industry standard for network discovery, security scanning, and vulnerability detection.  
It is used by penetration testers, system administrators, and security analysts to:

- Discover live hosts on a network
- Identify open ports and running services
- Detect operating systems and service versions
- Find vulnerabilities using NSE (Nmap Scripting Engine)

---

## 🎯 Why I Learned Nmap

Network scanning is the **first and most critical step** in any penetration test. Without proper enumeration, you cannot identify attack surfaces.  
I learned Nmap to:

- Understand how attackers discover vulnerable targets
- Perform internal and external network reconnaissance
- Automate vulnerability detection using NSE scripts
- Prepare for real-world security assessments

---

## 🛠️ What I Did with Nmap

In this repository, I have documented my **hands-on Nmap labs** including:

| Scan Type | What I Practiced |
|-----------|-------------------|
| **Host Discovery** | Finding live hosts on a network without port scanning |
| **SYN Stealth Scan** | Fast half-open scanning (less logging) |
| **TCP Connect Scan** | Full TCP handshake for accurate results |
| **UDP Scan** | Discovering open UDP ports (DNS, SNMP, etc.) |
| **Service Detection** | Identifying service versions (Apache, OpenSSH, SMB) |
| **OS Fingerprinting** | Guessing the target operating system |
| **NSE Scripts** | Running vulnerability detection scripts (e.g., EternalBlue) |
| **Performance Tuning** | Using timing templates (`-T4`) and packet rates for faster scans |

---

## 📂 What’s Inside This Repository

| File / Folder | Description |
|---------------|-------------|
| `README.md` | Complete guide with commands, screenshots, and use cases |
| `cheatsheet` | Quick reference of the most useful Nmap commands |
| `screenshots/` | Proof of work – real scan outputs from my lab |
| `examples/` | Real-world scanning scenarios with explanations |

---

> 💡 All scans were performed in an **isolated virtual lab** (VirtualBox) on my own systems. No production networks were.

---------------------

### Lets start understanding Nmap 

---

1. Live host discovery using ARP scan :

- When privileaged user tries to scan targets on local netwrok nmap uses ARP request.
- When privileaged user tries to scan target outside the local network nmap uses ICPM requests.
- When unprivileaged user tries to scan target outside the local network nmap uses TCP 3way handshake on port 443 and port 80

---

### Host Discovery :
- If you want to find live host without port scan : nmap -sN_ip address
- If you want to skip host discovery : nmap -Pn_ip address
- If you want nmap only ARP scanning without port scanning : nmap -PR -sn target (Here PR indicates that you want only ARP scanning)

---

### Host Discover using ICMP :
- ICMP request are used when host is on another subnet because ARP request dont cross Routers.
- But here ICMP have some issue because firewall and windows or server are configured to block unnecessary ICMP requests.
- So ICMP have 3 main types i mentioned below.

---

1. if you want to ICMP ping scan without port scan : nmap -PE -sn target.
2. As i said above ICMP is blocked by default we can use ICMP timestamp request : nmap -PP -sn target ( here PP stands for timestamp request)
3. Similialry nmap uses address mask queries  to use this command should be : nmap -PM -sn target.

---

### SUMMARY :
- Regarding icmp scan i listed all commands below
  1. To discover host using icmp echo : nmap -PE -sn target
     - This is the type 8 request.
     - Server reply with type 0 request.
     - Firewall can block
     - normal ping request
 ---

 
  2. To discover host using icmp timestamp : nmap -PP -sn target
     - Trhis is the type 13 request
     - Server send type 14 request in the form of current time
     - Always blocked by firewall but sometime allowed
     - When ping is blocked use timestamp
  ---

  
  3. To discover host using icmp address mask :nmap -PM -sn target
     - This is type 17 request
     - Server responds with type 18 reply with subnet mask adress
     - used when we want to know subnet mask
     - firewall blocks but sometime its allowed
     - used as last option when both of ping and timestamp is blocked.


   ---


   ### Commands :

- ARP Scan :	sudo nmap -PR -sn MACHINE_IP/24
- ICMP Echo Scan :	 nmap -PE -sn MACHINE_IP/24
- ICMP Timestamp Scan :	 nmap -PP -sn MACHINE_IP/24
- ICMP Address Mask Scan :	 nmap -PM -sn MACHINE_IP/24
- TCP SYN Ping Scan :	nmap -PS22,80,443 -sn MACHINE_IP/30
- TCP ACK Ping Scan :	 nmap -PA22,80,443 -sn MACHINE_IP/30
- UDP Ping Scan :	 nmap -PU53,161,162 -sn MACHINE_IP/30


  
  
  
