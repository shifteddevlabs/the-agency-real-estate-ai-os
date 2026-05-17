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
- `Blocking` missing information
- `Helpful` missing information
- `Source of truth`
- `Proof available`
- `Proof missing`
- `Reviewer needed`
- `Review reason`
- `Cannot proceed until`
- `Human Review` gate

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

## Handoff To Property Research

Use when a live deal needs more property context.

Include:

- Matter ID.
- Property address.
- Deal stage.
- Research question.
- Deadline.
- Source documents already available.

## Return To Orchestrator When

- The update touches lead status, research, and client communication at once.
- A deadline is urgent and ownership is unclear.
- A compliance or legal risk changes the plan.
