---
title: "TryHackMe – Brute It"
layout: single
collection: writeups
permalink: /writeups/tryhackme-brute-it/
classes: wide
tags: [tryhackme, brute-force, ssh, hydra]
---

![Brute It Screenshot](/assets/images/tryhackme-brute.png)

## Target
Brute-force login credentials over SSH

## Tools Used
- Hydra
- Nmap
- Kali Linux

## Steps
1. Scanned target using `nmap -sV`
2. Discovered open port 22 (SSH)
3. Ran Hydra to brute-force credentials
4. Gained shell access

## Lessons Learned
- Account lockout policies are essential
- Brute-force protection should be enforced at the server level

