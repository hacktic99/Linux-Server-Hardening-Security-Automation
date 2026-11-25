# Change plan and rollback template

> Complete this before changing a host. Copy it for each host and maintenance window.

## Change details

| Field | Value |
|---|---|
| Change ID | [ID] |
| Host alias / environment | [Redacted alias] |
| OS release / kernel | [Version] |
| System owner | [Role/name in private record] |
| Implementer / reviewer | [Roles] |
| Planned start/end | [Date, time, timezone] |
| Related ticket | [Reference] |
| Snapshot / backup reference | [Reference and time] |

## Purpose and scope
**Reason:** [Security objective or issue.]

**In scope:** [Exact configuration, package, service, interface, or account.]

**Out of scope:** [Explicit exclusions.]

**Expected result:** [Measurable outcome.]

## Pre-change checklist
- [ ] Authorisation and maintenance window confirmed.
- [ ] Application/service owner notified.
- [ ] Snapshot or tested backup completed.
- [ ] Console/out-of-band recovery access tested.
- [ ] Current SSH path and firewall zone recorded.
- [ ] Existing configuration and audit rules reviewed.
- [ ] Baseline evidence stored securely.
- [ ] Rollback trigger and operator agreed.

## Implementation record
| Step | Action / command | Expected result | Actual result | Evidence ID |
|---|---|---|---|---|
| 1 | [Action] | [Expected] | [After execution] | [ID] |
| 2 | [Action] | [Expected] | [After execution] | [ID] |
| 3 | [Action] | [Expected] | [After execution] | [ID] |

## Validation criteria
[Specify syntax tests, effective settings, second SSH session, remote network-flow tests, application health, audit event search, and exact pass conditions as relevant.]

## Rollback
**Trigger:** [When must the change stop or be reversed?]

**Steps:** [Exact restore/reversal procedure.]

**Recovery access:** [Reference to approved private procedure; do not include credentials.]

**Post-rollback tests:** [SSH, firewall, application, audit.]

**Owner:** [Role.]

## Risks and communications
| Risk | Impact | Mitigation | Owner |
|---|---|---|---|
| [Risk] | [Impact] | [Mitigation] | [Owner] |

## Approval and closure
| Role | Reference | Date | Decision |
|---|---|---|---|
| Change approver | [Reference] | [Date] | [Approved/rejected] |
| System owner | [Reference] | [Date] | [Acknowledged] |
| Implementer | [Reference] | [Date] | [Complete/rollback] |

**Final status:** [Successful / partially successful / rolled back / failed]

**Outstanding actions:** [Owner and due date.]
