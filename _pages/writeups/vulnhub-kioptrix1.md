---
title: "💣 VulnHub – Kioptrix Level 1"
excerpt: "Exploited an old Apache vulnerability to gain root access..."
image: /assets/images/vulnhub-kioptrix1.png
layout: single
collection: writeups
permalink: /writeups/vulnhub-kioptrix1/
tags: [vulnhub, kioptrix, privilege-escalation]
---

![Kioptrix 1 Screenshot](/assets/images/vulnhub-kioptrix1.png)

## 🎯 Target
- Gain root access on the Kioptrix Level 1 VM via a known Apache vulnerability and local privilege escalation.

## 🛠 Tools Used
- Nmap  
- Nikto  
- Metasploit  
- Netcat  
- Linux Exploit Suggester

---

## 🧭 Enumeration

### Step 1: Nmap Scan
```bash
nmap -sS -sV -A 192.168.1.112
