# T04 – Laptop flagged as noncompliant

**Short description:** Laptop flagged as noncompliant

**Description:** Hannah Brooks (Accounts Receivable Specialist) received a notice that her laptop is not compliant with company policy. Noncompliant devices may lose access to company resources.

| Field | Value |
|---|---|
| Incident | [INC0010004] |
| Caller | Hannah Brooks (Accounts Receivable Specialist) |
| Category | Hardware |
| Impact / Urgency | 3 – Low / 1 – High |
| Priority | 3 – Moderate |
| SLA | P3 Resolution – 3 business days ([met]) |
| Assigned group | Service Desk - Tier 1 |

## Request
> "I got an email saying my laptop isn't compliant."

## Triage
P3 – Moderate. A single device is affected; the user can still work but risks losing access to company data.

## Steps taken
1. In the Intune admin center, opened Devices → Windows → [MDPC] → Device compliance. The device was **Not compliant** under the policy `Test Policy`.
2. Compared the policy requirement with the device: the policy required a minimum OS version of [11.0.26200], and the device was running build [10.0.26200], more than one build below the requirement.
3. Confirmed the change history for the policy in the Intune audit log.
4. Lab fix: set the policy minimum to the device's current build. Production fix: the user installs the pending Windows update.
5. Synced the device from Settings → Accounts → Access work or school → Info → Sync.

## Verification
After sync, the device reported **Compliant** in Intune.

## Resolution notes
Cause: device OS build was below the compliance policy's minimum version. Fix: in production, install the pending Windows update and sync the device; in the lab, the policy minimum was aligned to the current build. Verified Compliant status in Intune.
