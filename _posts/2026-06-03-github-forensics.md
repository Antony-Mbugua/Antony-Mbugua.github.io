---
title: "Git Forensics CTF – Recovering Secrets from Git History"
layout: post
collection: writeups
permalink: /writeups/git-forensics-ctf/
date: 2026-03-09
categories: ["Writeups", "CTF"]
tags: [git, git-forensics, secrets-discovery, incident-response, cybersecurity]
image: /assets/images/writeups/git-forensics/git-forensics-cover.png
thumbnail: /assets/images/writeups/git-forensics/git-forensics-cover.png
icon: fas fa-code-branch
excerpt: "Recovering a hidden flag by analyzing Git commit history and repository logs."
description: "A Git forensics challenge demonstrating how sensitive credentials committed to a repository can be recovered from commit history using Git investigation techniques."
---

# Git Forensics CTF Writeup

## Objective
Identify a hidden flag inside a Git repository by analyzing commit history.

## Tools Used
- Git
- Linux Terminal
- Basic Git Forensics Techniques

---

## Challenge File

You can download the original challenge archive below:

[Download Challenge File](/assets/files/git-forensics-ctf/git_challenge.zip)

---

## Step 1: Extract the Challenge Files

![Step 1](/assets/images/writeups/git-forensics/step1.png)

The archive was extracted and the repository inspected. The `.git` directory confirmed that the project contains version control history.

---

## Step 2: Inspect Commit History

![Step 2](/assets/images/writeups/git-forensics/step2.png)

Using `git log --oneline`, we reviewed commit history to identify suspicious commits. One commit referenced a **secrets file containing an API key**.

---

## Step 3: Inspect the Commit Contents

![Step 3](/assets/images/writeups/git-forensics/step3.png)

Using `git show`, we examined the commit contents and discovered a hardcoded key.

---

## Captured Flag


---

## Security Lesson

This challenge demonstrates a common security mistake where developers commit sensitive credentials into Git repositories. Even if removed later, Git history still preserves the data.

Attackers frequently analyze repository history to recover leaked secrets.

### Mitigation
- Never commit secrets into repositories
- Use environment variables
- Implement secret scanning tools such as **GitLeaks** or **TruffleHog**

---

## Author
Antony Mbugua Githinji  
Cybersecurity Enthusiast | Cloud & Network Security | SOC & SIEM
