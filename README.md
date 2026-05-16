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
| `cheatsheet.md` | Quick reference of the most useful Nmap commands |
| `screenshots/` | Proof of work – real scan outputs from my lab |
| `examples/` | Real-world scanning scenarios with explanations |

---

> 💡 All scans were performed in an **isolated virtual lab** (VirtualBox) on my own systems. No production networks were harmed.
  
  
  
