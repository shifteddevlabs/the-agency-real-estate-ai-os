# Handoff Protocol

## What I Receive

- Executed contract details.
- Listing launch checklist.
- Deadline notes.
- Inspection, appraisal, title, lender, HOA, or closing updates.
- Document requests.
- Client or vendor messages that create tasks.

## What I Produce

- Transaction status.
- Verified and unverified date list.
- Checklist with owners.
- Blockers and escalations.
- Client update points for `03_client_communication/`.

## Required Packet Fields

Every handoff must preserve:

- `Matter ID`
- `Stage`
- `Return to`
- `Back reason`
- `Confidence`
- `Trail`
- `Stall trigger`
- `Next check`
- `Last touched by`
- `Blocking` missing information
- `Helpful` missing information
- `Source of truth`
- `Proof available`
- `Proof missing`
- `Reviewer needed`
- `Review reason`
- `Cannot proceed until`
- `Human Review` gate
- `Agency Standard` footer
- Lead/deal log update need

## Handoff To Client Communication

Use when the team needs a client update.

Include:

- Matter ID.
- What happened.
- What is next.
- What is waiting on whom.
- Any dates that are verified.
- Any dates that must be caveated.
- Exact language to avoid.
- Escalation owner if needed.
- Next check date.

## Handoff To Property Research

Use when a live deal needs more property context.

Include:

- Matter ID.
- Property address.
- Deal stage.
- Research question.
- Deadline.
- Source documents already available.
- Proof available and proof missing.

## Return To Orchestrator When

- The update touches lead status, research, and client communication at once.
- A deadline is urgent and ownership is unclear.
- A compliance or legal risk changes the plan.

## Process References

- Use `../support/reference/handoff-contracts.md` for universal handoff metadata.
- Use `../support/reference/agency-standard.md` before a deadline, checklist, escalation, or client update point moves forward.
- Use `../support/reference/lead-deal-log-template.md` after verified dates, blockers, proof changes, escalations, or client decisions.
- Use `../support/reference/deal-desk.md` signals for urgent deadlines, waiting items, source gaps, and stale transaction tasks.
