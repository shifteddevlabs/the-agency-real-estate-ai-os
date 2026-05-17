# Handoff Protocol

## What I Receive

- New inquiry text.
- Open-house notes.
- Referral notes.
- CRM lead records.
- Social or website form submissions.

If the orchestrator passes `lead_type: new` or `lead_type: returning`, use the scripted flows in `modes/new.md` or `modes/returning.md`. Otherwise default to the channel-specific scripts in `reference/first-contact-playbook.md`.

## What I Produce

- Lead summary.
- Lead temperature.
- Missing information.
- Suggested follow-up questions.
- Next best action.
- Handoff packet to research, communication, or transaction coordination.

## Required Packet Fields

Every handoff must preserve:

- `Matter ID`
- `Stage`
- `Blocking` missing information
- `Helpful` missing information
- `Source of truth`
- `Reviewer needed`
- `Review reason`
- `Cannot proceed until`
- `Human Review` gate

## Handoff To Property Research

Use when the lead needs property, neighborhood, or market context.

Include:

- Matter ID.
- Client criteria.
- Areas or addresses named by the client.
- Budget range.
- Timeline.
- Objective research questions.
- Fair-housing sensitivities to avoid.

## Handoff To Client Communication

Use when the next step is a reply, nurture note, meeting invite, or follow-up.

Include:

- Matter ID.
- Lead summary.
- Tone needed.
- Questions to ask.
- Call to action.
- Channel: email, text, call script, or DM.

## Handoff To Transaction Coordinator

Use only after the person is represented, under contract, or entering a live transaction process.

Include:

- Matter ID.
- Client name.
- Property address.
- Representation status.
- Contract or appointment status.
- Dates already verified by a human.

## Return To Orchestrator When

- The request mixes multiple owners.
- The lead is asking for something outside the team's scope.
- Compliance risk is too high to route directly.
