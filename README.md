# Linux-Server-Hardening-Security-Automation
This project demonstrates practical Linux security administration and automation using Bash scripting and Red Hat Enterprise Linux.

# Linux Server Hardening & Security Automation

## Overview

This project demonstrates practical Linux security administration and automation using Bash scripting and Red Hat Enterprise Linux.

The objective is to develop a reusable security hardening framework that helps administrators improve Linux server security, reduce vulnerabilities and maintain consistent security configurations.

## Objectives

- Automate Linux security configuration.
- Implement SSH security best practices.
- Configure firewall rules using Firewalld.
- Identify missing security patches.
- Audit user accounts and privileged access.
- Monitor important system configuration changes.
- Generate security compliance reports.

## Technologies

- Red Hat Enterprise Linux (RHEL)
- Bash scripting
- OpenSSH
- Firewalld
- SELinux
- Auditd
- Linux package management (DNF/YUM)
- Git

## Project Components

### 1. SSH Hardening
- Disable root SSH login.
- Disable password authentication where key-based access is configured.
- Configure SSH authentication policies.
- Restrict permitted users.

### 2. Firewall Configuration
- Configure Firewalld.
- Restrict unnecessary network services.
- Allow only approved ports and protocols.

### 3. Security Patching
- Identify missing security updates.
- Check installed package versions.
- Automate security patch reporting.

### 4. User Account Auditing
- Identify users with privileged access.
- Review sudo permissions.
- Identify inactive accounts.
- Audit password and account policies.

### 5. Security Reporting
- Generate system security reports.
- Record configuration changes.
- Identify potential security weaknesses.

## Repository Structure

```text
linux-server-hardening/
├── scripts/
│   ├── ssh-hardening.sh
│   ├── firewall-hardening.sh
│   ├── security-patching.sh
│   └── user-audit.sh
├── configs/
│   └── sshd_config.example
├── reports/
├── docs/
│   └── implementation-guide.md
└── README.md
```

## Learning Outcomes

This project provides practical experience in:

- Linux system security.
- Vulnerability management.
- Security automation.
- Enterprise server administration.
- Infrastructure hardening.
- Security auditing and compliance.

## Disclaimer

This project is intended for educational and laboratory purposes. Test all scripts in a non-production environment before deploying them to business-critical systems.
