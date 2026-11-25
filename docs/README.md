# Documentation index

This project follows a repeatable workflow: **assess → plan → back up → implement → validate → record → review**.

## Project documents
- [Project charter and objectives](project-charter.md)
- [End-to-end implementation guide](implementation-guide.md)
- [Project templates](templates/README.md)

## Tutorials
All seven practical tutorials are in [the tutorial guide](tutorials/README.md):
1. Lab preparation and baseline assessment
2. SSH hardening
3. Firewalld network hardening
4. Security patch assessment and installation
5. User and sudo auditing
6. auditd security event monitoring
7. Validation, evidence, and reporting

## Screenshots and diagrams
The SVG files in screenshots are illustrative diagrams and terminal mockups. They are not captured from a live RHEL host and must not be used as test evidence. Replace them with genuine, redacted captures from your lab when you run the exercises.

## Platform compatibility
RHEL 9 is the primary reference, and many concepts apply to RHEL 8. Package versions, defaults, OpenSSH directives, and audit behavior may differ. Treat RHEL 7/CentOS 7 as a separate compatibility task. Verify every command on the target release and follow local security policy.
