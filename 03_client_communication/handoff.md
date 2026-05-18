# Handoff Protocol

## What I Receive

- Lead summaries.
- Research briefs.
- Transaction updates.
- Client notes.
- Drafts needing polish.
- Compliance constraints.

## What I Produce

- Email drafts.
- Text drafts.
- Call scripts.
- Follow-up sequences.
- Client-ready summaries.
- Human review notes.

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
- `Reviewer needed`
- `Review reason`
- `Cannot proceed until`
- `Human Review` gate
- `Agency Standard` footer
- Lead/deal log update need

## Handoff To Lead Qualifier

Use when the communication reveals missing intake information.

Include:

- Matter ID.
- Questions answered.
- Questions still missing.
- Lead temperature changes.
- Any urgency or motivation shift.
- Next follow-up due if known.

## Handoff To Property Research

Use when a client asks a property, market, neighborhood, school, permit, or source-backed question.

Include:

- Matter ID.
- Exact client question.
- Draft context already shared.
- Facts that must be verified before another reply.
- Source or deadline recheck needed.

## Handoff To Transaction Coordinator

Use when a client message creates a deal task, deadline, document need, or vendor follow-up.

Include:

- Matter ID.
- Message summary.
- Required task.
- Due date if known.
- Human owner.
- Whether the client has been told anything yet.
- Client message due date if known.

## Return To Orchestrator When

- A request requires multiple specialists.
- Public-facing marketing needs a routing decision.
- Compliance risk changes the next owner.

## Process References

- Use `../support/reference/handoff-contracts.md` for universal handoff metadata.
- Use `../support/reference/agency-standard.md` before a draft is labeled ready for human review.
- Use `../support/reference/lead-deal-log-template.md` after a draft is created, approved, sent by a human, or blocked.
- Use `../support/reference/daily-operating-brief.md` signals for messages due, stale drafts, and Diana or broker review queues.
