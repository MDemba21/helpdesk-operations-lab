# Help Desk Operations Lab

Simulated Tier 1 service desk: 7 incidents and requests logged, worked, and resolved in ServiceNow using Microsoft Entra ID, Intune, and Exchange Online.

## Scenario
Tier 1 support for a fictional 15-person company with HR, Finance, and IT departments. Every request arrives as a ServiceNow incident, is prioritized with an Impact/Urgency matrix, tracked against an SLA, and closed with documented resolution notes. Escalations follow a written SOP.

## Environment
| Tool | Purpose |
|---|---|
| Microsoft 365 E5 (trial tenant) | Entra ID P1/P2, Intune, Exchange Online |
| ServiceNow Personal Developer Instance | Incident management, SLAs, assignment groups |
| Personal Windows PC | Enrolled in Intune for the device compliance ticket |

## Setup
- 15 users bulk-created from CSV with department, job title, and usage location
- Assigned security groups per department, plus an all-staff group
- Group-based licensing: E5 assigned to the all-staff group
- finance@ shared mailbox for the Finance team
- ServiceNow: Tier 1 and Tier 2 assignment groups, caller records, and four resolution SLAs (P1/P2 on a 24x7 clock, P3/P4 on business hours)
- [Escalation SOP](sop/escalation-sop.md)

## Tickets
| # | Incident | Ticket | Priority | Tools |
|---|---|---|---|---|
| T01 | INC0010001 | [New hire onboarding](tickets/T01-new-hire-onboarding.md) | 4 - Low | Entra ID, Exchange Online |
| T02 | INC0010002 | [Account locked out](tickets/T02-account-lockout.md) | 3 - Moderate | Entra ID sign-in logs |
| T03 | INC0010003 | [MFA reset after new phone](tickets/T03-mfa-reset.md) | 3 - Moderate | Entra ID, Temporary Access Pass |
| T04 | INC0010004 | [Laptop noncompliant](tickets/T04-device-compliance.md) | 3 - Moderate | Intune |
| T05 | INC0010005 | [Termination offboarding](tickets/T05-offboarding.md) | 2 - High | Entra ID, Exchange Online, Intune |
| T06 | INC0010006 | [Finance email outage (escalated)](tickets/T06-email-outage-escalation.md) | 1 - Critical | Exchange Online message trace, ServiceNow |
| T07 | INC0010007 | [User blocked from signing in](tickets/T07-sign-in-blocked.md) | 3 - Moderate | Sign-in logs, Conditional Access What If |

All 7 incidents resolved within SLA. Full export: [incident_tickets.csv](exports/incident_tickets.csv)

## Skills demonstrated
- Account lifecycle: onboarding and offboarding
- Password, lockout, and MFA recovery with identity verification
- Group-based access and licensing
- Shared mailbox access and mail flow troubleshooting
- Endpoint compliance in Intune
- Sign-in troubleshooting with error codes, Conditional Access, and What If
- Incident management: prioritization, SLAs, work notes, escalation with handoff

## Production notes
In a production environment, users would sync from Entra ID to ServiceNow automatically, and department groups would likely use dynamic membership based on HR attributes. Both were done manually here to show each step.
