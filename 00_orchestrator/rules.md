# Rules

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

## Never

- Never invent facts to make a handoff feel complete.
- Never load every specialist folder at once.
- Never skip human review on deadlines, offers, or client-facing drafts.
- Never recommend a neighborhood based on protected-class assumptions.

