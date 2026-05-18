# Daily Operating Brief

The Daily Operating Brief is the daily operating view for The Agency. It turns private lead/deal logs into one short briefing so Diana can see what needs attention without opening every chat or folder.

This is not a CRM, transaction platform, or official deal file. It is a working summary built from `lead-deal-logs/` and the latest handoff packets.

## When To Use It

Use the Daily Operating Brief when:

- Diana asks what needs attention today.
- A new chat needs the current state across several active matters.
- A lead or deal has gone quiet.
- A deadline, source check, client reply, or human review is due.
- More than one specialist touched the same matter.

## Beginner Prompt

```text
Use The Agency Daily Operating Brief.

Review these lead/deal logs and create today's briefing.

Show open actions, urgent risks, Diana decisions, stale items, client messages due, and anything that cannot move until a human verifies it.

[paste lead/deal logs]
```

If the AI can read files, ask:

```text
Use The Agency Daily Operating Brief.

Read the private logs in `lead-deal-logs/` and create today's briefing.
```

## Source Inputs

Use only:

- Current lead/deal logs.
- Current handoff packets.
- Diana or team member updates pasted into the chat.
- Verified source notes from property research or transaction coordination.

Do not invent deal state from memory. If a log is missing or stale, mark it stale.

## Daily Brief Format

```md
# Daily Operating Brief

Date:
Prepared from:

## Urgent Today

-

## Diana Decision Queue

-

## Client Messages Due

-

## Stale Or Waiting

-

## Source Or Deadline Rechecks

-

## Open Actions By Owner

### Diana
-

### Lead qualifier
-

### Property research
-

### Client communication
-

### Transaction coordinator
-

## Cannot Move Until

-

## Update These Logs

-
```

## Specialist Inputs

Each main specialist contributes a different signal to the Daily Operating Brief.

| Specialist | Adds to the brief |
|---|---|
| `01_lead_qualifier/` | Lead temperature, next follow-up, buyer or listing agreement status, poor-fit or represented-lead flags |
| `02_property_research/` | Source recheck dates, confidence level, research questions, source conflicts, client-ready or internal-only labels |
| `03_client_communication/` | Drafts waiting review, messages due, voice issues, broker-review needs, language-review needs |
| `04_transaction_coordinator/` | Verified deadlines, unverified deadlines, blockers, escalation owners, proof still needed |

The orchestrator may assemble the full brief, but each specialist should update the fields it owns before the brief is trusted.

## Status Labels

Use these labels in the brief and in lead/deal logs:

- `Active`: work is moving and the next owner is clear.
- `Waiting on client`: client must answer before the next step.
- `Waiting on Diana`: Diana must decide or review.
- `Waiting on source`: a fact, deadline, document, or professional answer is missing.
- `Stale`: no update after the next-check date.
- `Escalated`: broker, attorney, lender, title, inspector, or another qualified human owns the next step.
- `Paused`: work cannot continue safely.

## Decision Queue Rules

Put an item in Diana's decision queue when:

- A client-facing message needs judgment, not just proofreading.
- A deadline conflict or source conflict exists.
- A lead may already be represented.
- A buyer wants to see a property before buyer-representation status is confirmed.
- A seller or buyer asks for legal, tax, lending, valuation, inspection, or repair advice.
- A fair-housing, wire-fraud, privacy, advertising, or language-access flag is open.

## Stale Item Rules

Mark a matter stale when:

- `Next check date` has passed.
- `Last touched` is older than the urgency allows.
- A client message was drafted but not reviewed or sent.
- Research was completed but not used.
- A deadline was mentioned but not verified.
- A human escalation was opened but no resolution is recorded.

## What Not To Do

- Do not treat the Daily Operating Brief as the official record.
- Do not include wire instructions, account numbers, routing numbers, or private financial details.
- Do not summarize real private client details into a public repo.
- Do not mark a deadline verified unless the executed contract or official source is named.
- Do not mark a client message sent unless a human says it was sent.

## Save Or Update Prompt

After the brief is created, ask:

```text
Create the log updates needed from this Daily Operating Brief.

For each affected lead/deal log, give me the exact section to update and the reason.
```
