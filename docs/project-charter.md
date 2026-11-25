# Project charter – Linux Server Hardening & Security Automation

## Executive summary
This project defines a practical and evidence-led process for improving Linux server security. It focuses on remote administration, network exposure, patch management, identity and privilege review, security auditing, and reporting.

**Current repository status:** documentation and manual lab procedures are being established first. Executable hardening scripts and production-ready configuration files are future deliverables, not existing capabilities.

## Problem statement
Linux servers may accumulate unnecessary listening services, delayed security updates, overly broad administrative privileges, weak remote-access settings, and limited monitoring of sensitive changes. Inconsistent administration makes it difficult to reproduce changes and prove whether controls work.

The project applies a consistent lifecycle: assess the host, authorise and plan changes, preserve recovery options, implement one control area at a time, validate functionally, and retain evidence.

## Objectives and acceptance criteria

| ID | Objective | Acceptance criteria |
|---|---|---|
| OBJ-01 | Baseline assessment | OS/kernel, interfaces, listeners, services, firewall zones, SELinux, SSH settings, update status, users, and audit state are recorded |
| OBJ-02 | SSH hardening | sshd syntax passes; effective settings are reviewed; a second administrator login and required sudo test succeed |
| OBJ-03 | Network restriction | Active Firewalld zone rules match an approved allow-list; required flows work and unapproved paths are tested from relevant source networks |
| OBJ-04 | Security patching | Security advisories and proposed transaction are reviewed; result and reboot/restart requirements are recorded |
| OBJ-05 | Identity review | UID 0 accounts, privileged groups, sudo rules, and potentially stale accounts receive an owner decision |
| OBJ-06 | Change monitoring | Selected audit rules load and a known test event can be retrieved |
| OBJ-07 | Assurance reporting | Every control is marked Pass, Fail, Not tested, Not applicable, or Exception and linked to evidence |

## Scope

**In scope:** RHEL 8/9 lab systems (RHEL 9 primary); OpenSSH; Firewalld; DNF; local accounts and sudo; auditd; baseline collection; change control; validation; and reporting.

**Out of scope:** unattended production changes; automatic reboots; enterprise identity-provider changes; network architecture redesign; application-specific hardening; formal compliance certification; and any claim that these controls alone make a host secure.

## Deliverables
1. Project README and documentation index.
2. Project charter, objectives, scope, risks, and acceptance criteria.
3. End-to-end implementation guide.
4. Seven tutorials with verification and rollback guidance.
5. Illustrative architecture and terminal-style diagrams.
6. Change-plan, evidence-register, and assessment-report templates.
7. Future automation backlog with safety and testing requirements.

## Roles and responsibilities

| Role | Responsibility |
|---|---|
| System/lab owner | Owns the VM, access, backup, and application context |
| Implementer | Executes approved steps and records actual results |
| Security reviewer | Reviews settings, findings, exceptions, and evidence |
| Application owner | Confirms dependencies, maintenance window, and health |
| Change approver | Authorises scope, timing, risk, and rollback |

In a personal lab one person may perform multiple roles. Record that honestly rather than implying independent approval.

## Risks and mitigations

| Risk | Impact | Mitigation |
|---|---|---|
| SSH changed before key access is proven | Remote lockout | Keep session open, test a second login, retain console access |
| Firewall rule removes management path | Remote administration unavailable | Inspect active zone and source networks; add and test required access first |
| Patch disrupts an application | Service outage | Review transaction and schedule with the service owner |
| Service account disabled as stale | Batch/application failure | Validate dependency and owner before changing account |
| Audit rules create excessive events | Storage growth and noise | Scope rules, monitor capacity, define retention |
| Example differs from local policy | Security or availability regression | Test on a lab VM and follow approved policy |

## Definition of done
The lab run is complete when the scope and host are recorded, a recovery point exists, baseline evidence is retained, each in-scope control has a test result, owners review identity changes, service health is checked, and the report links each conclusion to genuine evidence.
