---
title: "TryHackMe – Brute It"
layout: single
collection: writeups
permalink: /writeups/tryhackme-brute-it/
classes: wide
tags: [tryhackme, brute-force, ssh, hydra]
---

![Brute It Screenshot](/assets/images/tryhackme-brute-it.png)

## 🧠 Target
- Brute-force login credentials over SSH  
- Hash cracking  
- Privilege escalation

## 🛠 Tools Used
- Hydra  
- Nmap  
- Kali Linux

## 🧭 Steps

1. **Scanned target using `nmap -sV`**  
   This revealed the SSH port was open on 22.

   ![Nmap Scan](/assets/images/writeups/brute-it/nmap-scan.png)

2. **Discovered open port 22 (SSH)**  
   Verified the service running and confirmed it's OpenSSH.

   ![SSH Port Confirmation](/assets/images/writeups/brute-it/ssh-port.png)

3. **Ran Hydra to brute-force credentials**  
   Used a common username/password list to brute-force SSH.

   ![Hydra Brute Force](/assets/images/writeups/brute-it/hydra.png)

4. **Gained shell access**  
   Logged in successfully and obtained user access to the system.

   ![Shell Access](/assets/images/writeups/brute-it/shell-access.png)

## 📘 Lessons Learned
- Account lockout policies are essential  
- Brute-force protection (e.g., fail2ban, rate-limiting) should be enforced  
- Avoid using default or guessable credentials
