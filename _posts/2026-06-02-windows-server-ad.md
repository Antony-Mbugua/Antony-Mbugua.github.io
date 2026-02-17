<img width="1073" height="671" alt="image" src="https://github.com/user-attachments/assets/053b3ee2-0f03-4eb3-840b-4b4bb07b442a" />---
layout: post
title: "Windows Server 2025 Virtualization & Active Directory Deployment Lab"
date: 2026-02-07
categories: [Systems, Infrastructure]
tags: [Windows Server, Active Directory, Virtualization, Networking]
image:
  path: /assets/images/projects/windows-server/ws14.png
---

# Windows Server 2025 Virtualization & Active Directory Deployment Lab

## Overview

In this lab, I implemented a complete Windows Server 2025 virtual environment and deployed Active Directory Domain Services (AD DS). The objective was to simulate a real-world enterprise infrastructure setup while strengthening my skills in virtualization, networking, domain management, and troubleshooting.

This walkthrough documents the entire process — from ISO preparation to a fully operational domain controller.

---

## Objectives

- Install Windows Server 2025 in a virtual machine  
- Configure virtual networking  
- Assign static IP addressing  
- Install Active Directory Domain Services  
- Promote a domain controller  
- Validate domain functionality  
- Troubleshoot deployment issues  

![VM iMAGE](/assets/images/projects/windows-server/ws1.png)
---

## Environment Setup

### Hardware

- Virtualization-capable PC  
- Minimum 16 GB RAM  
- SSD storage  

### Software

- VirtualBox / VMware  
- Windows Server 2025 ISO  

---

# Phase 1 — Windows Server Virtual Machine Setup

## Step 1 — Download Windows Server ISO

I downloaded the Windows Server 2025 evaluation ISO from Microsoft.

![Windows Server 2025 Installation Page](/assets/images/projects/windows-server/ws-install.png) 

---

## Step 2 — Create Virtual Machine

I created a new VM with:

- Allocated RAM  
- CPU cores  
- Virtual disk storage  

![VM Resources](/assets/images/projects/windows-server/ws-vm.png) 

---

## Step 3 — Attach ISO & Boot VM

Mounted the ISO and launched installation.

![VM Boot](/assets/images/projects/windows-server/ws2.png)

![Windows Server Setup](/assets/images/projects/windows-server/ws3.png)

---

# Phase 2 — Windows Server Installation

## Step 4 — OS Installation

Selected Desktop Experience and completed installation.

![Setup 1](/assets/images/projects/windows-server/ws4.png)
![Setup 2](/assets/images/projects/windows-server/ws5.png)
![Setup 3](/assets/images/projects/windows-server/ws6.png)

---

## Step 5 — Administrator Setup

Configured administrator credentials and initial login.

![Amin Logins](/assets/images/projects/windows-server/ws12.png)

---

# Phase 3 — Network Configuration

## Step 6 — Adapter Configuration

Verified NAT/bridged networking inside VM settings.

![VM Network/Adapetr Configs](/assets/images/projects/windows-server/ws-adapter.png)

---

## Step 7 — Static IP Assignment

Configured static IP, subnet mask, gateway, and DNS.

![Server Network Adapter Settings](/assets/images/projects/windows-server/ws-network-ad.png)  
![Static IP](/assets/images/projects/windows-server/ws-ipv4-static-ip.png)  

---

## Step 8 — Connectivity Testing

Validated network connectivity.

![Ping Test](/assets/images/projects/windows-server/ws-ping.png)   

---

# Phase 4 — Server Preparation

## Step 9 — Rename Server

Renamed the server to reflect domain controller role.

![Server Rename](/assets/images/projects/windows-server/ws-rename.png)   

---

## Step 10 — Restart System

Restarted to apply configuration.

![Restart to Apply Setup](/assets/images/projects/windows-server/ws14.png)  

---

# Phase 5 — Active Directory Installation

## Step 11 — Add Roles & Features

Installed Active Directory Domain Services via Server Manager.

![Add Roles](/assets/images/projects/windows-server/ws-add-roles.png)  
![AD Roles](/assets/images/projects/windows-server/ws-AD-roles-installation-page.png) 
![Installation Type](/assets/images/projects/windows-server/ws-installation-type-select-role-based.png)  
![Server Selection](/assets/images/projects/windows-server/ws-server-select-from-pool(SVR-LAB-TECH).png)  
![Server Roles](/assets/images/projects/windows-server/ws-AD-Domain-Service-select.png)  

---

## Step 12 — Installation Confirmation

Verified successful installation.

![Installation](/assets/images/projects/windows-server/ws-Insatallation(AD).png) 
![Success Install](/assets/images/projects/windows-server/ws-success-install.png)  
![AD Installed](/assets/images/projects/windows-server/AD-installed.png)  
---

# Phase 6 — Domain Controller Promotion

## Step 13 — Promote Server

Created a new forest:


![Promoting Server](/assets/images/projects/windows-server/ws-promote-to-a-domain-controller.png)  
![Deployment Config](/assets/images/projects/windows-server/ws-AD-Deployment-Configuration.png)  

---

## Step 14 — Directory Services Restore Mode

Configured DSRM password.

📸 Screenshot 19 — DSRM configuration  

---

## Step 15 — Final Promotion

Completed domain controller setup.

📸 Screenshot 20 — Promotion validation  

---

## Step 16 — Automatic Restart

Server rebooted into domain environment.

📸 Screenshot 21 — Post-promotion login  

---

# Phase 7 — Active Directory Verification

## Step 17 — Open AD Tools

Accessed administrative consoles.

📸 Screenshot 22 — AD Users & Computers  

---

## Step 18 — Domain Validation

Confirmed domain structure.

📸 Screenshot 23 — Domain tree  

---

## Step 19 — Test User Creation

Created sample users.

📸 Screenshot 24 — User creation  

---

## Step 20 — Policy Verification

Verified Group Policy availability.

📸 Screenshot 25 — GPO console  

---

# Phase 8 — Troubleshooting & Validation

## Step 21 — Network Troubleshooting

Resolved connectivity issues caused by adapter misconfiguration.

📸 Screenshot 26 — Adapter correction  

---

## Step 22 — Static IP Revalidation

Ensured domain services function correctly.

📸 Screenshot 27 — IP verification  

---

## Step 23 — Service Confirmation

Verified AD services are running.

📸 Screenshot 28 — Services console  

---

## Step 24 — Final Validation

Confirmed domain controller health.

📸 Screenshot 29 — System validation  

---

## Step 25 — Operational Environment

Final working environment.

📸 Screenshot 30 — Fully operational domain  

---

# Key Skills Demonstrated

- Virtualization deployment  
- Windows Server installation  
- Static network configuration  
- Active Directory deployment  
- Domain controller promotion  
- Infrastructure troubleshooting  
- Documentation discipline  

---

# Challenges & Solutions

**Issue:** VM networking failure  
**Resolution:** Adapter correction and IP reconfiguration.

This reinforced structured troubleshooting methodology.

---

# Outcome

I successfully deployed a fully functional Windows Server domain controller within a virtualized environment. The system mirrors enterprise infrastructure and forms the foundation for advanced labs including:

- Group Policy deployment  
- Certificate Services  
- Client domain joining  
- Hybrid identity environments  

---

# Author

**Antony M Githinji**  
Infrastructure & Systems Lab Implementation

