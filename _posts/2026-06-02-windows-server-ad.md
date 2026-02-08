---
layout: post
title: "Windows Server Active Directory Lab"
date: 2026-02-07
categories: [Systems, Infrastructure]
tags: [Windows Server, Active Directory, Virtualization, Networking]
image:
  path: /assets/img/projects/windows-ad.png
---

# Windows Server Active Directory Lab

## Overview

This project documents my hands-on implementation of a Windows Server virtual environment and the deployment of Active Directory Domain Services (AD DS). The goal was to simulate a real-world enterprise infrastructure setup while strengthening my skills in virtualization, networking, and centralized identity management.

This lab mirrors how organizations deploy domain controllers, manage users, and enforce policies within a secure environment.

---

## Objectives

- Install Windows Server in a virtual machine  
- Configure VM networking  
- Implement static IP addressing  
- Deploy Active Directory Domain Services  
- Promote a domain controller  
- Validate domain functionality  
- Troubleshoot connectivity issues  

---

## Tools & Technologies

- Windows Server 2025 (Desktop Experience)  
- VirtualBox / VMware  
- Active Directory Domain Services  
- Group Policy Management  
- Virtual networking (NAT)  
- Static IP configuration  

---

## Implementation Summary

### 1. Virtual Machine Setup
I created a virtual machine with allocated CPU, RAM, and storage resources, then attached the Windows Server ISO.

### 2. Windows Server Installation
Installed the Desktop Experience edition and configured administrator access.

### 3. Network Configuration
Configured NAT networking and assigned a static IP to support domain services.

### 4. Active Directory Deployment
Installed AD Domain Services and promoted the server to a domain controller.

**Domain created:**  
`ad.techrealm.local`

### 5. Verification
Confirmed domain functionality using Active Directory administrative tools and test user creation.

---

## Key Skills Demonstrated

- Server virtualization  
- Windows Server installation  
- Network configuration  
- Static IP addressing  
- Active Directory deployment  
- Domain controller promotion  
- Troubleshooting VM networking  
- Technical documentation  

---

## Challenges & Solutions

**Issue:** VM network connectivity failure  
**Solution:** Verified adapter configuration and corrected static IP settings.

This reinforced troubleshooting methodology in virtual environments.

---

## Screenshots

*(Add screenshots here)*

- VM creation  
- Static IP configuration  
- AD installation  
- Domain controller promotion  
- Active Directory console  

---

## Outcome

The lab environment successfully simulates enterprise identity infrastructure. I gained practical experience in deploying and managing Active Directory within a virtualized setup.

Future expansion includes:

- Group Policy implementation  
- Certificate Services  
- Client domain joining  
- Hybrid cloud integration  

---

## Author

**Antony M Githinji**  
Systems & Infrastructure Lab Project
