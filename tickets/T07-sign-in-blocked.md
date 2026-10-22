# T07 – User can't sign in

**Short description:** "You don't have access to this" when opening email

**Description:** Priya Shah (Recruiter, HR) cannot open Outlook on the web. After entering her password and approving MFA, she receives "You don't have access to this – Your sign-in was successful but you don't have permission to access this resource."

| Field | Value |
|---|---|
| Incident | [INC0010007] |
| Caller | Priya Shah (Recruiter) |
| Category | Software |
| Impact / Urgency | 3 – Low / 1 – High |
| Priority | 3 – Moderate |
| SLA | P3 Resolution – 3 business days ([met]) |
| Assigned group | Service Desk - Tier 1 |

## Request
> "I keep getting an error that I don't have access when I try to open my email."

## Triage
P3 – Moderate. A single user is blocked from email, with no wider impact.

## Steps taken
1. Collected the error details from the user's "More details" screen (error code **53003** and correlation ID).
2. Reviewed Entra ID sign-in logs for the user. The failed sign-in to One Outlook Web showed error **53003** (blocked by Conditional Access). The Conditional Access tab showed policy **CA002 - Block SG-Blocked** with result **Failure**.
3. Confirmed with the Conditional Access **What If** tool that CA002 applies to the user with Grant control **Block access**.
4. Checked the `SG-Blocked` group's audit log to see who added the user (
MamadouDemba@ExamLabPractice2435.onmicrosoft.com).
5. Confirmed with the user's manager, Dana Whitfield (HR Manager), that the block was not intentional before making any change.
6. Removed the user from `SG-Blocked`.

What If inputs: User Priya Shah · Cloud app Office 365 Exchange Online · Platform Windows · Client app Modern authentication clients

## Verification
User signed in again. Sign-in log shows **Success**; on the Conditional Access tab, CA001 (Require MFA) shows Success and CA002 shows **Not Applied**.

Note on the sign-in log: the earlier Interrupted and Success entries are from before the user was added to `SG-Blocked`.

## Resolution notes
Cause: user was a member of `SG-Blocked`, which is targeted by a Conditional Access policy that blocks access.
Fix: after confirming with the user's manager that the block was not intended, removed the user from the group.
Verified: successful sign-in with CA002 no longer applied.
