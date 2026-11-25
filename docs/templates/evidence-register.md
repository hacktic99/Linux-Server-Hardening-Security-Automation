# Evidence register

> Use one row per artefact or test. Keep raw evidence in restricted storage; publish only sanitised material.

| ID | Control | Host alias | Date/time + TZ | Command / test | Expected result | Actual result / status | File / secure reference | Redacted? |
|---|---|---|---|---|---|---|---|---|
| EV-001 | Baseline | [Alias] | [Time] | OS/kernel/interface inventory | Host baseline recorded | [Result] | [Path] | [Y/N] |
| EV-002 | SSH | [Alias] | [Time] | sshd -t and sshd -T | Syntax valid; target settings effective | [Result] | [Path] | [Y/N] |
| EV-003 | SSH | [Alias] | [Time] | Second-session key login | Named admin login and sudo work | [Result] | [Path] | [Y/N] |
| EV-004 | Firewall | [Alias] | [Time] | firewall-cmd active zones/listing | Rules match approved allow-list | [Result] | [Path] | [Y/N] |
| EV-005 | Firewall | [Alias] | [Time] | Remote flow tests | Approved paths work; others restricted | [Result] | [Path] | [Y/N] |
| EV-006 | Patching | [Alias] | [Time] | DNF advisory/transaction review | Outcome and restart need recorded | [Result] | [Path] | [Y/N] |
| EV-007 | Identity | [Alias] | [Time] | UID 0, wheel, sudoers review | Privileged access reviewed by owner | [Result] | [Path] | [Y/N] |
| EV-008 | auditd | [Alias] | [Time] | auditctl and ausearch test | Rule loaded and event searchable | [Result] | [Path] | [Y/N] |
| EV-009 | Application | [Alias] | [Time] | Owner health check | Application healthy after change | [Result] | [Path] | [Y/N] |

## Evidence handling checklist
- [ ] Host alias and environment are clear.
- [ ] Timestamp and timezone included.
- [ ] Command/test is reproducible.
- [ ] Actual result is not copied from an illustrative example.
- [ ] Secrets, private keys, tokens, and customer data are removed.
- [ ] Evidence ID is referenced by the report.
- [ ] Review and retention details are recorded.

## Screenshot capture guidance
Capture the command and enough output to show its result, while redacting sensitive values. Save text output as well as an image because it is searchable. The mockups in docs/screenshots are not proof that a real host passed.
