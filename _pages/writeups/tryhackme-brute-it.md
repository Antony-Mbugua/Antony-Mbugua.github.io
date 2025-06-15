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
- Kali Linux machine

## 🧭 Steps
1. **Started the target machine `10.10.34.33`**  


   ![Tarhet Machine](/assets/images/brute-it/target-machine.png)

2. **Scanned target using `nmap -sS -sV  10.10.34.33`**  
   -This revealed two open ports, 22 and 80.
   -The SSH port was open on 22.

   ![Nmap Scan](/assets/images/brute-it/nmap.png)

3. **Discovered;**  
 -The version of SSH running is
   **OpenSSH 7.6p1**

 -The version of Apache running is
   **2.4.29**

 -The linux distro running is
   **Ubuntu**

   ![Ubuntu running](/assets/images/brute-it/ubuntu.png)


4. **Searched for hidden directories on the web server.**  
  I used dirbuster command “dirsearch -u http://10.10.34.33”

   ![Dirsearch](/assets/images/brute-it/dirsearch.png)

   I discovered the hidden directory as **"/admin"**

5. **Visited the port 80 of the target/admin**  
   On the web browser, i visited http://10.10.34.3/admin. Amazing!. I got a an admin login page.

   ![Admin](/assets/images/brute-it/hidden-admin-login-page.png)


4. **Checked more details about the page on browser devtools**  
   By clicking F12 on my attack machine while on the page, I came across an interesting footprint.
   The username which was admin!! LOL

   We can see the username is admin we now need the password!!!

   ![Login leads](/assets/images/brute-it/User-login-info-devtools.png)


4. **Ran Hydra to brute-force credentials**  
   Used a common username/password list to brute-force SSH.

   I tried command "hydra -l admin -P /usr/share/wordlists/rockyou.txt 10.10.34.33 http-post-form "/admin/:user=^USER^&pass=^PASS^login=^Login:Username or password invalid"" but the output was slow.

   ![Hydra Brute Force](/assets/images/brute-it/slow-output.png)

   I opted to use command “hydra -l admin -P /usr/share/wordlists/rockyou.txt -e nsr -t 16 -vV 10.10.245.181 http-post-form "/admin/:user=^USER^&pass=^PASS^&login=Login:Username or password invalid" “
   
    ![Hydra Brute Force](/assets/images/brute-it/hydra.png)

   Finally I got the password
[80][http-post-form] host: 10.10.245.181   login: admin   password: xavier


    ![Hydra Brute Force](/assets/images/brute-it/hydra1.png)

6. **Gained shell access**  
   Logged in successfully and obtained user access to the system.
  
   Flag: THM{brut3_f0rce_is_e4sy}


   ![Shell Access](/assets/images/brute-it/shell-access.png)

## 📘 Lessons Learned
- Account lockout policies are essential  
- Brute-force protection (e.g., fail2ban, rate-limiting) should be enforced  
- Avoid using default or guessable credentials
