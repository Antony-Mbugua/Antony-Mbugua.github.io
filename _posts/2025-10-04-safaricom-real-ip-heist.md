title: "🧪 Safaricom PwnZone – Real IP Heist"
layout: post
collection: writeups
permalink: /writeups/safaricom-real-ip-heist/
date: 2025-10-04
categories: [Writeups]
tags: [web, headers, pwnzone]
image: /assets/images/writeups/real-ip-heist/safaricom-real-ip-heist.png
thumbnail: /assets/images/writeups/real-ip-heist/safaricom-real-ip-heist.png
icon: fas fa-network-wired
excerpt: "Abused trust in X-Forwarded-For / X-Real-IP headers to escalate access and retrieve the flag."
description: "Exploit of server trusting client-supplied X-Forwarded-For/X-Real-IP headers, obtaining Admin access and the flag."
---

![Real IP Heist Screenshot](/assets/images/writeups/real-ip-heist/safaricom-real-ip-heist.png)

# Real IP Heist — Safaricom PwnZone

## Target
A small Flask/Werkzeug web app with a login form. The client-side code sets a fixed `X-Forwarded-For` header when sending the login request with `fetch()`. The server uses request headers to decide whether a user is allowed the `Admin` access level.

## Short summary (TL;DR)
The application trusts client-supplied `X-Forwarded-For` / `X-Real-IP` headers to decide whether a request originates from an internal/trusted IP (localhost). By sending requests that include `X-Forwarded-For: 127.0.0.1` (and `X-Real-IP: 127.0.0.1`), we can bypass client-side restrictions and set `access_level=Admin` in a POST — then visit `/admin` to read the flag.

Flag obtained: `safctf{c0f1ec1fccb2de4a03031037251f21a7}`
