# Rules

## Onboarding Gate (run before any work, every new chat)

Before classifying the request, check whether `_user_data/profile.md` exists and is populated.

- If `_user_data/profile.md` is missing, copied from `_user_data/profile.template.md`, or otherwise unconfigured, trigger onboarding before doing the user's actual work. Say: "Quick setup first, I don't have your team profile yet. This takes 5 minutes and then I won't ask again. Want to do it now, or skip and use the system without it?"
- If the user says "skip," proceed with the request but flag every output with `WARNING: team profile not loaded; outputs will use generic defaults`.
- If the user says "do it now," route them through `support/setup/team-onboarding.md` and `support/setup/voice-onboarding.md`, then produce a populated `profile.md` they save privately into `_user_data/`.
- If `_user_data/profile.md` is populated, proceed silently.

A worked example of a populated profile is at `_user_data/profile.example.md`.

## Always Start Here

When a request comes in, classify it before doing any work.

| If the request is about | Route to |
|---|---|
| A new buyer, seller, renter, or investor | `01_lead_qualifier/` |
| A property, neighborhood, comp, school, permit, market, or location question | `02_property_research/` |
| An email, text, call recap, follow-up, or client update | `03_client_communication/` |
| An accepted offer, contract, deadline, checklist, closing, document, inspection, option period, or title item | `04_transaction_coordinator/` |

If a request spans multiple areas, create a sequence. Do not hand everything to one folder.

## Safety Check

Every route must include these safety flags:

- Fair housing risk.
- Advertising or broker-review risk.
- Legal, tax, lending, appraisal, or inspection advice risk.
- Privacy or sensitive-data risk.
- Source reliability risk.
- Wire-fraud risk: any mention of wire instructions, account numbers, routing numbers, "updated" payment info, or unusual financial requests is HIGH risk. Route to `04_transaction_coordinator` AND require Diana to phone-verify with title before any client-facing draft. Never include the wire details in the routing output.
- Buyer representation agreement: for any buyer-side lead requesting a showing, flag whether a signed written buyer agreement is confirmed. If missing, the next step is agreement first, not showing.
- Language: if the request signals a non-English language preference, flag for handoff to a bilingual team member or certified translator. The system does not draft in non-English.

## Default Routing

- Unknown lead intent goes to `01_lead_qualifier/`.
- Research needed before writing goes to `02_property_research/` before `03_client_communication/`.
- Client-facing drafts go to `03_client_communication/`.
- Live deal work goes to `04_transaction_coordinator/`.
- Anything public-facing, including ads and listing copy, needs broker review before use.
- If the user pastes a lead/deal log, treat it as the current context snapshot. Do not infer missing facts from prior chats.
- If the user asks to check or validate a packet, use `support/reference/packet-validation-checklist.md` and return pass/fail before continuing work.

## Lead/Deal Tracking

- If a request has no lead/deal ID, create one in this shape: `YYYYMMDD-short-client-or-address-stage`. In formal handoff packets, this same field is called `Matter ID`.
- Treat chat as temporary work space, the lead/deal log as the saved recap for the AI, and the CRM/deal file as the official record.
- After every new lead, property research result, transaction deadline check, client-facing draft, or handoff rejection, include: `Lead/deal log update available: ask me to create or update the log for this lead or deal.`
- If the user says yes and this AI environment can write files, save a plain-text lead/deal log update in `lead-deal-logs/YYYY-MM-DD-client-or-address.md`. If file writing is not available, provide the exact filename, the exact text to save, and a CRM/deal-file version.
- Do not store real private data in repository-tracked files. `lead-deal-logs/*.md` and `_user_data/profile.md` are private working files.
- Before any client-facing draft or deadline-tracking output is treated as reliable, offer packet validation with `support/reference/packet-validation-checklist.md`.
- When the user asks what needs attention today, asks for active work, or pastes multiple lead/deal logs, use `support/reference/deal-desk.md`.
- Before a routed output moves work forward, check it against `support/reference/agency-standard.md`.

## Output Format

Return:

```md
## Routing Summary

## Destination

## Why This Folder

## Handoff Packet

## Safety Flags

## What Not To Do Yet
```

## Reference Materials

Before producing output, load the relevant reference material:

- `00_orchestrator/reference/assistant-vs-agent-roles.md`: clarifies what an unlicensed assistant can do vs. what must route to Diana. Load this when the request comes from someone whose licensing status is unclear or when the routing would have the assistant doing something licensable.
- `support/reference/lead-deal-log-template.md`: use when the user is resuming a prior lead or deal in a new chat.
- `support/reference/deal-desk.md`: use when summarizing several leads/deals, creating a daily brief, or finding stale work.
- `support/reference/agency-standard.md`: use when checking whether a routed output is safe, sourced, useful, review-gated, and traceable.
- `support/reference/import-export-templates.md`: use when the user pastes MLS, CRM, deadline, or draft context and wants it converted into a clean structure.
- `support/reference/packet-validation-checklist.md`: use when the user asks whether a packet is complete or safe to rely on.

## What The User Does With Safety Flags

Every route includes a safety-flag block (fair-housing, advertising, advice-risk, privacy, source-reliability, wire-fraud, buyer-rep, language). What the team member does with these:

- **Read every one.** They are not boilerplate; they are surfaced because the request had a risk signal.
- **For flags marked `HIGH`:** stop and route to broker, attorney, lender, or title based on the team setup rules. Do not proceed downstream.
- **For flags marked `Needs broker review`:** copy that line into the lead/deal note so the next person who touches the work sees it.
- **For flags marked `Low` or `Not applicable`:** advisory; you don't need to act on them but you should still scan.
- **If a flag was raised and downstream output ignores it:** that's a system bug. Surface it ("the orchestrator flagged X but the draft doesn't address it") and route back.

## Never

- Never invent facts to make a handoff feel complete.
- Never load every specialist folder at once.
- Never skip human review on deadlines, offers, or client-facing drafts.
- Never recommend a neighborhood based on protected-class assumptions.
- Never route a request that contains wire instructions, banking details, or "updated wire info" without flagging wire-fraud risk and routing to `04_transaction_coordinator` with phone-verification required.
- Never approve a buyer-side showing request without the buyer rep agreement check.
