# T05 – Termination offboarding

**Short description:** Termination: Chris Morgan, effective 5:00 PM today

**Description:** Dana Whitfield (HR Manager) reported that Chris Morgan (HR Generalist) is leaving the company today, effective 5:00 PM. All access must be removed, and Dana needs access to Chris's email.

| Field | Value |
|---|---|
| Incident | [INC0010005] |
| Caller | Dana Whitfield (HR Manager) |
| Category | Inquiry / Help |
| Impact / Urgency | 2 – Medium / 1 – High |
| Priority | 2 – High |
| SLA | P2 Resolution – 8 hours, 24x7 ([met]) |
| Assigned group | Service Desk - Tier 1 |

## Request
> "Chris Morgan in HR is leaving today, effective 5:00 PM. Their manager needs access to their email."

## Triage
P2 – High. Same-day termination deadline; access must be removed on time.

## Steps taken
Completed in this order:
1. **Blocked sign-in** (Entra ID → Edit properties → Account enabled unchecked) to stop new sign-ins.
2. **Revoked sessions** to end any sign-ins already in progress.
3. **Reset the password**; the new password was not recorded or shared.
4. **Converted the mailbox to a shared mailbox** and granted Dana Whitfield Read and manage (Full Access). Done before license removal, since removing the license from a user mailbox starts its deletion.
5. **Set an automatic reply** for internal and external senders directing them to Dana Whitfield.
6. **Removed group memberships** (`SG-HR`, `SG-AllStaff`); the E5 license was removed automatically with `SG-AllStaff`.
7. **Checked Intune** for devices assigned to the user; none found.

## Verification
User Overview shows sign-in blocked. Mailbox listed as shared with Dana Whitfield delegated. No devices assigned to the user in Intune.

## Resolution notes
Offboarding completed per checklist by the 5:00 PM deadline. Access removed, email retained as a shared mailbox for the manager, and automatic reply in place.

Automatic reply text:
> Thank you for your message. Chris Morgan is no longer with the company. For HR matters, please contact Dana Whitfield at dana.whitfield@ExamLabPractice2435.onmicrosoft.com.
