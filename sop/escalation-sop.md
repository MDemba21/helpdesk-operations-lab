# Escalation SOP – Service Desk

## Purpose
Defines what Tier 1 resolves, when an incident is escalated to Tier 2, and how handoffs and bridge calls are handled.

## Priority and SLA reference
| Priority | Example | Resolution target | Clock |
|---|---|---|---|
| P1 – Critical | Outage affecting a department or more | 4 hours | 24x7 |
| P2 – High | Single user fully blocked from working | 8 hours | 24x7 |
| P3 – Moderate | User impaired, workaround exists | 3 business days | 8-5 weekdays |
| P4 – Low | Requests and minor issues | 5 business days | 8-5 weekdays |

## Tier 1 scope
Tier 1 resolves:
- Password resets and account lockouts (after identity verification)
- MFA method resets and Temporary Access Passes
- Onboarding and offboarding per checklist
- Group, license, and shared mailbox access requests
- Device compliance issues with a known fix

## Escalation triggers
Reassign to **Service Desk - Tier 2** when any of the following apply:
- The incident is P1
- Multiple users or a whole department are affected
- No resolution after 30 minutes of troubleshooting
- The fix requires permissions Tier 1 does not hold
- The cause is unknown after standard checks

## Handoff requirements
Before reassigning, work notes must include:
1. Caller and contact method
2. Impact and scope (who and how many are affected)
3. Time the issue started
4. Steps already taken and their results
5. Error messages or codes, exactly as shown

Tier 1 informs the caller that the incident was escalated and when to expect the next update.

## Bridge calls
- **When:** any P1 affecting multiple users
- **Who:** Tier 1 analyst, Tier 2 engineer, lead of the affected team
- **During:** Tier 1 records timeline and decisions
- **After:** log in work notes: start and end time, attendees, summary, next update time

## Closure
Before resolving, confirm the fix with the caller and record the root cause and resolution in resolution notes. For P1 incidents, include prevention steps.
