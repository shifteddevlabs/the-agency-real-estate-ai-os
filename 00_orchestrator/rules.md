# Rules

## Onboarding Gate (run before any work, every new chat)

Before classifying the request, check `_user_data/profile.md`.

- If the file still says `PLACEHOLDER — replace this file during onboarding` (or is otherwise unconfigured), trigger onboarding before doing the user's actual work. Say: "Quick setup first — I don't have your team profile yet. This takes 5 minutes and then I won't ask again. Want to do it now, or skip and use the system without it?"
- If the user says "skip," proceed with the request but flag every output with `WARNING: team profile not loaded; outputs will use generic defaults`.
- If the user says "do it now," route them through `setup/team-onboarding.md` and `setup/voice-onboarding.md`, then produce a populated `profile.md` they save into `_user_data/`.
- If `_user_data/profile.md` is populated (not the placeholder), proceed silently.

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

## Compliance Scan

Every routing output must include these flags:

- Fair housing risk.
- Advertising or broker-review risk.
- Legal, tax, lending, appraisal, or inspection advice risk.
- Privacy or sensitive-data risk.
- Source reliability risk.
- Wire-fraud risk: any mention of wire instructions, account numbers, routing numbers, "updated" payment info, or unusual financial requests is HIGH risk. Route to `04_transaction_coordinator` AND require Diana to phone-verify with title before any client-facing draft. Never include the wire details in the routing output.
- Buyer representation agreement: for any buyer-side lead requesting a showing, flag whether a signed buyer rep agreement exists. If missing, next step is sign-agreement-first, not show-the-home (post-NAR 2024 requirement).
- Language: if the request signals a non-English language preference, flag for handoff to a bilingual team member or certified translator. The system does not draft in non-English.

## Default Routing Logic

- Unknown lead intent goes to `01_lead_qualifier/`.
- Research needed before writing goes to `02_property_research/` before `03_client_communication/`.
- Client-facing drafts go to `03_client_communication/`.
- Live deal work goes to `04_transaction_coordinator/`.
- Anything public-facing, including ads and listing copy, needs broker review before use.

## Output Format

Return:

```md
## Routing Summary

## Destination

## Why This Folder

## Handoff Packet

## Compliance Flags

## What Not To Do Yet
```

## Reference Materials

Before producing output, load the relevant reference material from `00_orchestrator/reference/`:

- `assistant-vs-agent-roles.md` — clarifies what an unlicensed assistant can do vs. what must route to Diana. Load this when the request comes from someone whose licensing status is unclear or when the routing would have the assistant doing something licensable.

## What The User Does With Compliance Flags

Every routing output includes a compliance-flag block (fair-housing, advertising, advice-risk, privacy, source-reliability, wire-fraud, buyer-rep, language). What the team member does with these:

- **Read every one.** They are not boilerplate; they are surfaced because the request had a risk signal.
- **For flags marked `HIGH`:** stop and route to broker, attorney, lender, or title per the escalation matrix. Do not proceed downstream.
- **For flags marked `Needs broker review`:** copy that line into the deal-file note for this matter so the next person who touches the deal sees it.
- **For flags marked `Low` or `Not applicable`:** advisory; you don't need to act on them but you should still scan.
- **If a flag was raised and downstream output ignores it:** that's a system bug. Surface it ("the orchestrator flagged X but the draft doesn't address it") and route back.

## Never

- Never invent facts to make a handoff feel complete.
- Never load every specialist folder at once.
- Never skip human review on deadlines, offers, or client-facing drafts.
- Never recommend a neighborhood based on protected-class assumptions.
- Never route a request that contains wire instructions, banking details, or "updated wire info" without flagging wire-fraud risk and routing to `04_transaction_coordinator` with phone-verification required.
- Never approve a buyer-side showing request without the buyer rep agreement check.

