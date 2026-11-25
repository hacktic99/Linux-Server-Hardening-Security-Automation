# End-to-end implementation guide

## Operating model
Follow **authorise → prepare → baseline → plan → implement → validate → evidence → close**. Change one control area at a time so failures can be isolated and reversed.

## Pre-change checklist
- [ ] Host alias, environment, OS release, kernel, and IP recorded.
- [ ] System owner, technical contact, and approval identified.
- [ ] Maintenance window and application dependencies confirmed.
- [ ] VM snapshot or tested backup completed.
- [ ] Console/out-of-band recovery access tested.
- [ ] Existing SSH port and administrator access path confirmed.
- [ ] Active Firewalld zones and required flows documented.
- [ ] Existing SSH drop-ins, audit rules, and configuration management reviewed.
- [ ] Evidence directory created with restrictive permissions.

## Phase 1 – Discovery
Complete the baseline tutorial. Capture host identity, interfaces, routes, listening services, firewall zones, SELinux state, SSH effective settings, DNF advisory status, account inventory, and audit state. Take a recoverable VM snapshot.

## Phase 2 – SSH
Confirm a named administrator can authenticate with the approved public key before disabling password or keyboard-interactive authentication. Back up the configuration, inspect included files and Match blocks, validate syntax, inspect effective settings, then reload.

**Gate:** A second SSH session succeeds and approved sudo tasks work. Keep the original session open until this is confirmed.

## Phase 3 – Network exposure
Map interfaces to active zones and create an approved inbound flow list. Preserve management access, add/test replacement access first, then remove only explicitly unauthorised services or ports.

**Gate:** Management and application flows work from the intended source networks. A local firewall listing alone is not proof of external exposure.

## Phase 4 – Patching and identity
Review repository health, security advisories, package transaction impact, and reboot/service restart needs. Review privileged and stale accounts with owners; do not infer that an account is unused just because its last interactive login is old.

**Gate:** Every update, exception, and account action has an owner and recorded outcome.

## Phase 5 – Auditing and reporting
Review existing audit configuration, add only scoped rules, generate a known test event, and retrieve it. Complete the evidence register and assessment report.

**Gate:** Each report statement links to a timestamped artefact. Untested controls are not reported as passed.

## Backup example
Before editing SSH configuration, create a protected timestamped copy:

~~~bash
sudo install -m 0600 -o root -g root /etc/ssh/sshd_config \
  "/root/sshd_config.pre-hardening.$(date +%Y%m%d-%H%M%S)"
~~~

Record the backup path. Check whether configuration management owns the file; a local edit may be overwritten.

## Rollback principles
- **SSH:** use console or the working session; restore the backup, run sshd syntax validation, reload, and retest.
- **Firewalld:** reverse only approved changes or use the tested restore process; immediately retest SSH and application paths.
- **Patching:** use tested snapshot/backup or package recovery procedures. Downgrades may not reverse data/schema changes.
- **Accounts:** restore access only after checking identity source and dependencies.
- **auditd:** remove only rules introduced by the exercise. Do not flush organisation-wide audit rules.

If a validation gate fails, stop, preserve logs, notify the owner, and use the approved rollback.

## Minimum proof by area

| Area | Required validation |
|---|---|
| SSH | Syntax valid, effective settings reviewed, second login and sudo pass |
| Firewall | Active zones match allow-list; tests from required source networks pass |
| Patching | Repository/advisory review recorded; transaction and restart impact assessed |
| Identity | Privileged accounts and sudo access reviewed with owners |
| auditd | Rule loaded, known event retrievable, audit health/storage reviewed |
| Overall | Application health passes; failures and residual risks documented |

## Future automation backlog
1. Read-only inventory script with structured output.
2. SSH audit mode that detects drift without silently rewriting local policy.
3. Firewalld allow-list comparison.
4. DNF advisory report mode; apply mode requires explicit approval.
5. User/sudo audit with operator-supplied service-account exclusions.
6. auditd deployment with conflict detection and rollback.
7. Consolidated report generator and shell tests.

Scripts should include dry-run/read-only mode, prerequisite checks, meaningful exit codes, logging, no embedded secrets, version awareness, and explicit rollback. Destructive changes require operator confirmation.
