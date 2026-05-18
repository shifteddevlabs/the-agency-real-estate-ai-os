# Lead/Deal Log Template

Use one lead/deal log per lead, client, property, or deal. This gives the AI enough memory to pick up a new chat without guessing.

Do not store private client data in a public repo. Keep real lead/deal logs in `lead-deal-logs/`, your private AI project, your CRM notes, Google Drive deal folder, or your transaction system.

Recommended filename:

```text
lead-deal-logs/YYYY-MM-DD-client-or-address.md
```

If your AI app can write files, ask it to save the log for you. If it cannot, ask for the exact filename and text, plus a "CRM notes version" you can paste into the official lead or deal record.

## Beginner Prompt

```text
Create or update the lead/deal log for this lead.

If you can write files, save it as `lead-deal-logs/YYYY-MM-DD-client-or-address.md`.

If you cannot write files, give me the exact filename, the exact text to save, and a CRM notes version.
```

## Filled Example

```md
# Lead/Deal Log

Lead/deal ID: 20260518-alex-east-austin-buyer-intake
Client or lead: Alex, referred by Mike
Stage: New buyer lead, intake incomplete
Assigned human owner: Diana
Last updated: 2026-05-18

## Current Status

- Mike referred Alex by text.
- Alex is moving to Austin in October.
- Budget signal is under $750K.
- Area signal is East Austin.
- Pre-approval is represented by referrer but not verified.
- Alex contact info is missing.

## Known Facts

- Source: Mike referral text.
- Buyer-rep agreement status is unknown.
- Language preference is unknown.

## Blocking Missing Information

- Alex's phone or email.
- Whether Alex has signed a buyer representation agreement.
- Whether Alex is already represented by another agent.

## Source And Proof State

- Source of truth: Mike referral text.
- Source checked at: 2026-05-18.
- Needs recheck before: sending a direct message to Alex or discussing showings.
- Proof available: referral text.
- Proof missing: Alex contact info, buyer-rep agreement status.

## Compliance Flags

- Fair housing: Low based on current facts.
- Advertising or broker-review: Not applicable.
- Legal, tax, lending, inspection, or appraisal advice: Not applicable.
- Privacy or sensitive data: Keep contact info in CRM, not public files.
- Wire-fraud: Not applicable.
- Buyer representation or listing agreement: Buyer-rep status unknown, do not schedule showings.
- Language: Unknown.

## Last Handoff Note

From: 00_orchestrator
To: 01_lead_qualifier
Matter ID: 20260518-alex-east-austin-buyer-intake
Stage: New buyer lead, referral intake
Next owner: Lead qualifier

## Client-Safe Drafts

- Draft reply to Mike asking for Alex's contact info.
- Draft first message to Alex, held until contact info and review.

## Decision Trail

- Date: 2026-05-18
  - Decision: Do not propose showings until buyer-rep status is known.
  - Decided by: System compliance rule, human to verify.
  - Source: Orchestrator buyer-rep flag.
  - Follow-up needed: Diana or assigned agent reviews reply before sending.
```

## Blank Template

```md
# Lead/Deal Log

Lead/deal ID:
Client or lead:
Stage:
Assigned human owner:
Last updated:

## Current Status

-

## Known Facts

-

## Blocking Missing Information

-

## Source And Proof State

- Source of truth:
- Source checked at:
- Needs recheck before:
- Proof available:
- Proof missing:

## Compliance Flags

- Fair housing:
- Advertising or broker-review:
- Legal, tax, lending, inspection, or appraisal advice:
- Privacy or sensitive data:
- Wire-fraud:
- Buyer representation or listing agreement:
- Language:

## Last Handoff Note

Paste the most recent complete handoff note here. If it came from a specialist folder, it may use the formal packet label `Matter ID`.

## Client-Safe Drafts

Paste only approved or draft-labeled client messages here. Never paste wire instructions.

## Decision Trail

- Date:
  - Decision:
  - Decided by:
  - Source:
  - Follow-up needed:
```

## How To Use It

At the start of a new chat, paste:

```text
Use The Agency.

Here is the current lead/deal log:
[paste lead/deal log]

Continue from this state. Do not assume anything missing. Tell me the next safest step.
```

## When To Update It

- After a new lead is qualified.
- After property research is refreshed.
- After a deadline is verified from an executed contract.
- After Diana, broker, title, lender, attorney, or a client makes a decision.
- Before starting a new chat on the same lead or deal.

## Plain Text Or Database?

Use a plain text markdown file for v1. It is readable, easy to paste into chat, and does not require installation.

A database could make sense in a future app. For this folder-based version, plain text is faster, easier, and less intimidating for a busy real estate team.
