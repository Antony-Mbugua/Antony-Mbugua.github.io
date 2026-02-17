---
layout: post
title: "Windows Server 2025 Active Directory Deployment Lab"
date: 2026-02-07
categories: [Systems, Infrastructure]
tags: [Windows Server, Active Directory, Virtualization, DNS, Networking, Writeups]
image:
  path: /assets/images/projects/windows-server/ws14.png
---

# Windows Server 2025 Active Directory Deployment Lab

## Executive Summary

This lab demonstrates the deployment of a Windows Server 2025 Domain Controller within a virtualized environment. The objective was to simulate a real-world enterprise identity infrastructure by implementing:

- Virtual machine provisioning
- Static network configuration
- Active Directory Domain Services (AD DS)
- DNS integration
- Domain controller promotion
- Service validation and troubleshooting

The result is a fully functional domain controller capable of supporting centralized authentication, policy enforcement, and identity management.

---

# 1. Infrastructure Architecture

## Deployment Model

- **Single Forest**
- **Single Domain**
- **Single Domain Controller**
- **AD-Integrated DNS**
- **Static IP Addressing**

This configuration mirrors foundational enterprise infrastructure used in small to medium-sized organizations.

---

# 2. Environment Setup

## Hardware

- Virtualization-capable workstation  
- Minimum 16 GB RAM  
- SSD storage  

## Software

- Hypervisor: VirtualBox / VMware  
- Windows Server 2025 ISO (Desktop Experience)  

---

# 3. Virtual Machine Provisioning

## Windows Server ISO Acquisition

The official Windows Server 2025 evaluation ISO was downloaded directly from Microsoft.

![Windows Server ISO Download](/assets/images/projects/windows-server/ws-install.png)

> Screenshot: Official Microsoft evaluation page confirming secure ISO acquisition.

---

## Virtual Machine Creation

A new virtual machine was created with adequate compute resources to support directory services.

![VM Resource Allocation](/assets/images/projects/windows-server/ws-vm.png)

> Screenshot: VM configuration showing assigned RAM, CPU cores, and disk storage.

Proper resource allocation ensures stable AD DS and DNS operation.

---

## ISO Mounting and Boot

The ISO was attached to the virtual optical drive and the VM booted to begin installation.

![VM Boot](/assets/images/projects/windows-server/ws2.png)

> Screenshot: VM successfully booting from mounted ISO.

---

# 4. Windows Server Installation

## OS Selection

The **Desktop Experience** edition was selected to allow GUI-based administrative configuration.

![Windows Setup 1](/assets/images/projects/windows-server/ws3.png)

> Screenshot: Initial Windows Server setup interface.

![Windows Setup 2](/assets/images/projects/windows-server/ws4.png)

> Screenshot: OS edition selection screen.

![Windows Setup 3](/assets/images/projects/windows-server/ws5.png)

> Screenshot: Installation progress.

---

## Administrator Configuration

The local Administrator account password was configured during initial setup.

![Administrator Login](/assets/images/projects/windows-server/ws12.png)

> Screenshot: First successful login to Windows Server environment.

---

# 5. Network Configuration

## Virtual Network Adapter Verification

The VM network adapter was configured to ensure connectivity between the server and host network.

![VM Adapter Configuration](/assets/images/projects/windows-server/ws-adapter.png)

> Screenshot: Virtual network adapter settings within hypervisor.

---

## Static IP Address Assignment

Domain Controllers require static IP addressing to ensure consistent DNS resolution and service discovery.

![Network Adapter Settings](/assets/images/projects/windows-server/ws-network-ad.png)

> Screenshot: Network adapter configuration interface.

![Static IPv4 Configuration](/assets/images/projects/windows-server/ws-ipv4-static-ip.png)

> Screenshot: Static IP, subnet mask, gateway, and DNS server configuration.

The server was configured to use its own static IP as the primary DNS server — a requirement for AD-integrated DNS.

---

## Connectivity Testing

Network reachability was validated using Ping testing.

![Ping Test](/assets/images/projects/windows-server/ws-ping.png)

> Screenshot: Successful ping confirming network connectivity.

---

# 6. Server Preparation

## Hostname Configuration

The server was renamed to reflect its infrastructure role.

![Server Rename](/assets/images/projects/windows-server/ws-rename.png)

> Screenshot: System rename configuration.

---

## Restart to Apply Changes

A restart was performed to apply hostname and network modifications.

![System Restart](/assets/images/projects/windows-server/ws14.png)

> Screenshot: System reboot applying configuration updates.

---

# 7. Active Directory Installation

## Adding Roles and Features

Active Directory Domain Services (AD DS) was installed using Server Manager.

![Add Roles Wizard](/assets/images/projects/windows-server/ws-add-roles.png)

> Screenshot: Server Manager role installation wizard.

![Role Selection](/assets/images/projects/windows-server/ws-AD-Domain-Service-select.png)

> Screenshot: Selection of Active Directory Domain Services.

![Installation Confirmation](/assets/images/projects/windows-server/ws-success-install.png)

> Screenshot: Successful AD DS role installation confirmation.

---

# 8. Domain Controller Promotion

## Forest Creation

The server was promoted as the first Domain Controller in a new forest.

![Promote to Domain Controller](/assets/images/projects/windows-server/ws-promote-to-a-domain-controller.png)

> Screenshot: Promotion wizard initiation.

![Deployment Configuration](/assets/images/projects/windows-server/ws-AD-Deployment-Configuration.png)

> Screenshot: New forest configuration.

---

## Directory Services Restore Mode (DSRM)

A DSRM password was configured for offline Active Directory maintenance and disaster recovery.

> Screenshot: DSRM configuration during promotion process.

---

## Prerequisite Validation & Promotion

The system performed prerequisite checks to validate DNS configuration and forest readiness.

> Screenshot: Promotion validation results.

After successful validation, the server was promoted to Domain Controller.

---

## Post-Promotion Reboot

The system automatically rebooted to complete AD initialization.

> Screenshot: Post-promotion login showing domain-qualified administrator account.

---

# 9. Active Directory Verification

## Active Directory Users and Computers

The ADUC console was opened to verify domain structure.

> Screenshot: Active Directory Users and Computers console.

---

## Domain Structure Validation

Default containers and built-in security groups were verified.

> Screenshot: Domain tree structure.

---

## Test User Creation

A sample domain user was created to validate directory functionality.

> Screenshot: Domain user creation.

---

## Group Policy Management

The Group Policy Management Console (GPMC) was accessed to confirm policy administration capability.

> Screenshot: Group Policy Management Console.

---

# 10. Service & Health Validation

## Network Troubleshooting

Connectivity issues were resolved by correcting adapter configuration and revalidating IP settings.

> Screenshot: Corrected adapter configuration.

---

## Service Verification

Critical services were verified to confirm domain health:

- DNS Server
- Netlogon
- Kerberos Key Distribution Center (KDC)
- Active Directory Domain Services

> Screenshot: Services console confirming operational status.

---

## Final Validation

Domain functionality was confirmed through:

- Successful domain login
- User object visibility
- DNS resolution
- Active Directory tool accessibility

> Screenshot: Fully operational domain controller environment.

---

# Skills Demonstrated

- Virtual infrastructure provisioning  
- Windows Server deployment  
- Static IP and DNS configuration  
- Active Directory Domain Services implementation  
- Forest and domain creation  
- Domain controller promotion  
- Enterprise troubleshooting methodology  
- Structured technical documentation  

---

# Conclusion

This lab successfully implemented a fully functional Windows Server 2025 Domain Controller within a virtualized environment.

The deployment establishes a foundational enterprise identity infrastructure capable of supporting:

- Centralized authentication
- Group Policy enforcement
- Domain-based resource management
- Future integration with client systems and additional domain controllers

This implementation reinforces core competencies in systems administration, infrastructure engineering, and enterprise identity architecture.
