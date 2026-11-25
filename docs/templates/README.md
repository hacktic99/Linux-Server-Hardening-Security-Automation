# Project templates

Copy and complete these templates for each lab run. Replace all prompts with actual information and store sensitive artefacts in restricted storage.

## Change plan and rollback
Record host alias, OS/kernel, scope, owner, approver, maintenance window, backup/snapshot, pre-change checks, implementation steps, validation criteria, rollback trigger, rollback steps, and final outcome.

## Evidence register
Use one row per artefact with unique ID, control, host alias, date/time/timezone, command or test, expected result, actual result, evidence filename/secure reference, and redaction status.

Suggested evidence IDs:
- EV-001 baseline inventory
- EV-002 SSH syntax/effective settings
- EV-003 second-session SSH login
- EV-004 Firewalld active-zone rules
- EV-005 remote network-flow tests
- EV-006 DNF advisory/transaction review
- EV-007 user and sudo review
- EV-008 auditd test event
- EV-009 application health check

## Security assessment report
Include executive summary, scope, method, limitations, control status, findings, change summary, exceptions, residual risks, evidence index, and reviewer sign-off.

## Result status definitions
- **Pass:** test performed and acceptance criterion met.
- **Fail:** test performed and criterion not met.
- **Not tested:** no reliable test was performed.
- **Not applicable:** the control does not apply, with rationale.
- **Exception:** authorised deviation exists, with owner and review date.

Never use illustrative SVG terminal images as proof that a live host passed. Capture genuine output and redact secrets, customer details, personal identifiers, hostnames/IPs where appropriate.
