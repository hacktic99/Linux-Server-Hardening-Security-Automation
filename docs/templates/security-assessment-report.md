# Linux server security assessment report

> Template only. Replace every prompt with verified information. Do not mark an untested control as passed.

## 1. Executive summary
- **Assessment date/time:** [Date, timezone]
- **Environment:** [Lab / test / production]
- **Host alias:** [Redacted alias]
- **Platform:** [RHEL release and kernel]
- **Assessor:** [Role]
- **Overall result:** [Actual findings, limitations, residual risk]
- **Key risks:** [Verified findings]
- **Recommended priorities:** [Immediate / planned]

## 2. Scope and method
**In scope:** [Hosts, interfaces, services, accounts, control areas.]

**Out of scope:** [Exclusions.]

**Methods:** [Configuration review, command checks, functional tests, audit event generation, owner review.]

**Limitations:** [Unavailable logs, incomplete network visibility, untested services, unsupported OS.]

## 3. Control results
| Control | Status | Observation | Evidence ID | Owner / due date |
|---|---|---|---|---|
| Baseline inventory | [Status] | [Result] | [ID] | [Owner/date] |
| SSH | [Status] | [Result] | [ID] | [Owner/date] |
| Firewalld | [Status] | [Result] | [ID] | [Owner/date] |
| Security patching | [Status] | [Result] | [ID] | [Owner/date] |
| User and sudo review | [Status] | [Result] | [ID] | [Owner/date] |
| auditd | [Status] | [Result] | [ID] | [Owner/date] |
| Application health | [Status] | [Result] | [ID] | [Owner/date] |

Use Pass, Fail, Not tested, Not applicable, or Exception and define local variations.

## 4. Findings
### FIND-001 – [Short title]
- **Severity:** [Critical / High / Medium / Low / Informational]
- **Asset/service:** [Host alias]
- **Observation:** [What was actually observed]
- **Risk:** [Impact and exposure]
- **Evidence:** [Evidence ID]
- **Recommendation:** [Specific corrective action]
- **Owner / target date:** [Role / date]
- **Status:** [Open / in progress / closed / exception]

[Repeat for each finding.]

## 5. Change and validation summary
| Change | Result | Validation | Rollback? |
|---|---|---|---|
| SSH | [Result] | [Test] | [Yes/no] |
| Firewall | [Result] | [Test] | [Yes/no] |
| Patching | [Result] | [Test] | [Yes/no] |
| Identity | [Result] | [Test] | [Yes/no] |
| auditd | [Result] | [Test] | [Yes/no] |

## 6. Exceptions and residual risk
| Exception | Business reason | Compensating control | Approver | Review date |
|---|---|---|---|---|
| [Exception] | [Reason] | [Control] | [Role] | [Date] |

## 7. Conclusion and sign-off
[State what was tested, what improved, what remains unresolved, and who accepts residual risk. Avoid claims such as fully secure or compliant unless a separate formal assessment supports them.]

| Reviewer | Role | Date | Comments |
|---|---|---|---|
| [Reference] | System owner | [Date] | [Comments] |
| [Reference] | Security reviewer | [Date] | [Comments] |

## Appendix – Evidence index
[Link the completed evidence register. Keep sensitive artefacts in approved private storage.]
