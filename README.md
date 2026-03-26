# 🚀 Apex Logistics Group – Enterprise IT Infrastructure & Systems Integration Lab

## 📌 Overview

This project simulates the design, deployment, and management of a full-scale **enterprise IT environment** for a logistics company, *Apex Logistics Group*.

The goal is to replicate real-world responsibilities of a **Systems Administrator / IT Support Engineer**, including infrastructure setup, identity management, system integration, automation, monitoring, and troubleshooting.

This lab demonstrates how multiple systems interact within an enterprise environment and how IT teams maintain, secure, and automate operations.

---

## 🧠 Objectives

* Build a multi-server enterprise IT environment from scratch
* Implement centralized identity management using Active Directory
* Integrate Windows and Linux systems for unified authentication
* Automate user provisioning and system tasks
* Deploy internal applications and databases
* Monitor system performance and configure alerting
* Simulate real-world IT support scenarios and troubleshooting workflows

---

## 🏢 Company Scenario

**Apex Logistics Group** is a growing logistics company managing warehouse operations, dispatch teams, and internal business functions.

The company requires:

* Secure access control across departments
* Centralized user management
* Internal systems for operations and requests
* Reliable infrastructure with monitoring and backups

I'm acting as a **Junior Systems Administrator**, responsible for building and maintaining this environment.

---

## 🏗️ Lab Architecture

The environment consists of multiple virtual machines configured within a private network:

* **Windows Server 2022**

  * Active Directory Domain Services (AD DS)
  * DNS & DHCP

* **Windows Client**

  * Domain-joined endpoint for users

* **Linux Server (AlmaLinux/Ubuntu)**

  * Integrated with Active Directory
  * Hosts internal services and applications

* **Optional Services**

  * Web server (Apache/Nginx)
  * Database (MySQL/PostgreSQL)
  * Monitoring tools (Netdata/Nagios)

---

## 🔗 Systems Integration

This lab focuses heavily on integrating systems to simulate real enterprise workflows:

* Active Directory authentication across Windows and Linux
* Automated user provisioning using HR data (CSV + scripts)
* Web application connected to a backend database
* Monitoring systems generating alerts based on system health
* Ticketing scenarios triggering automated responses

---

## 📊 Project Phases

The project is divided into structured phases:

1. **Infrastructure & Networking**
   Virtual machines, IP configuration, and connectivity setup

2. **Active Directory & Identity Management**
   Domain setup, users, groups, and Group Policy

3. **Endpoint Management**
   Domain-joined clients and user access validation

4. **File Server & Permissions**
   Shared drives and role-based access control

5. **Linux Deployment & Integration**
   Linux server setup and AD integration (SSSD/LDAP)

6. **Web Application & Database**
   Internal application deployment and backend integration

7. **Automation & HR Integration**
   User provisioning using scripts and scheduled tasks

8. **Monitoring & Alerting**
   System performance tracking and alert configuration

9. **Logging & Security Hardening**
   Log collection, firewall rules, and access control

10. **Backup & Disaster Recovery**
    Data protection and recovery simulations


---

## 📸 Documentation & Screenshots

All configurations, outputs, and troubleshooting steps are documented with screenshots:

```
/screenshots/
    ├── phase-1/
    ├── phase-2/
    ├── phase-3/
```

Each phase includes:

* Setup screenshots
* Command outputs
* Errors and resolutions

---

## ⚙️ Technologies Used

* **Operating Systems:** Windows Server, Windows Client, Linux (AlmaLinux/Ubuntu)
* **Identity Management:** Active Directory, LDAP, SSSD
* **Networking:** DNS, DHCP, TCP/IP, NAT
* **Scripting:** PowerShell, Bash
* **Web & Database:** Apache/Nginx, MySQL/PostgreSQL
* **Virtualization:** VirtualBox
* **Version Control:** Git & GitHub

---

## 💼 Skills Demonstrated

* System Administration (Windows & Linux)
* IT Support & Troubleshooting
* Identity & Access Management (IAM)
* Network Configuration & Debugging
* Systems Integration
* Automation & Scripting
* Monitoring & Incident Response
* Security Hardening & Best Practices




## 📌 Future Enhancements

* Multi-site Active Directory (branch offices)
* VPN integration for remote access
* Cloud integration (AWS/Azure)
* Advanced SIEM implementation
* Containerization (Docker)
* Azure Arc

---

# ONGOING PROJECT

## 🙌 Author

**Ekom**
M.S. Computer Science | Systems Administration & Cloud Enthusiast

---
