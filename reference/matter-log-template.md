# Matter Log Template

Use one matter log per lead, client, property, or deal. This gives the AI enough memory to pick up a new chat without guessing.

Do not store private client data in a public repo. Keep real matter logs in your private workspace or transaction system.

```md
# Matter Log

Matter ID:
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

## Last Handoff Packet

Paste the most recent complete handoff packet here.

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

Here is the current matter log:
[paste matter log]

Continue from this state. Do not assume anything missing. Tell me the next safest step.
```

## When To Update It

- After a new lead is qualified.
- After property research is refreshed.
- After a deadline is verified from an executed contract.
- After Diana, broker, title, lender, attorney, or a client makes a decision.
- Before starting a new chat on the same matter.
