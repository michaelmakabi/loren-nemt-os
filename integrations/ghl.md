# GoHighLevel — Integration Runbook

GHL is the orchestration spine. See `ghl/` for the full build spec:
- [`pipelines-and-stages.md`](../ghl/pipelines-and-stages.md)
- [`tags-and-segments.md`](../ghl/tags-and-segments.md)
- [`custom-fields.md`](../ghl/custom-fields.md)
- [`workflows.md`](../ghl/workflows.md)

## Snapshot strategy
- Maintain a master "Loren AI NEMT" snapshot in GHL.
- Every new client sub-account is created by importing this snapshot.
- Sub-account customization is post-import only: branding, custom field values, phone number routing.

## Snapshot contents (kept current)
- Pipelines: Ride Lifecycle, Facility Account
- Tags: full tag taxonomy from `tags-and-segments.md`
- Custom fields: full schema from `custom-fields.md`
- Workflows: W5–W14 (per-client) from `workflows.md`
- SMS / email templates: confirmations, reminders, reactivation
- Calendar: dispatcher / owner / facility-account
- Forms: ride request, facility bulk request, NPS

## Sub-account provisioning (per onboarded operator)
1. Create sub-account from snapshot via API.
2. Inject custom field values from kickoff form.
3. Configure Retell webhook URLs.
4. Configure Twilio (or Retell-provided) phone number routing.
5. Test end-to-end: form submit → contact created → workflow fires.

## Master account (Loren AI sales) — kept separate
- Pipelines: NEMT Operators, Operator Onboarding
- Workflows: W1–W4
- Calendar: strategy-call slots for Master Makabi / sales rep
