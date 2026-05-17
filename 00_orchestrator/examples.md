# Examples

## Example 1, New Buyer Lead

User request:

```text
Alex texted from Zillow. Wants to buy in Austin under 800k, maybe East Austin, moving in 90 days.
```

Orchestrator output:

```md
## Routing Summary
This is a new buyer lead with budget, location interest, and timeline.

## Destination
`01_lead_qualifier/`

## Why This Folder
The next job is to capture missing qualification details before research or drafting.

## Handoff Packet
From: 00_orchestrator
To: 01_lead_qualifier
Client or lead: Alex
Matter: New buyer inquiry
Urgency: Medium, 90-day timeline
Current status: Unqualified lead

## Known Facts
- Interested in buying in Austin.
- Budget mentioned: under 800k.
- Possible area interest: East Austin.
- Timeline: around 90 days.

## Missing Information
- Financing or pre-approval status.
- Must-haves and deal breakers.
- Current agent relationship.
- Preferred contact method.

## Compliance Flags
- Fair housing: avoid steering language about neighborhood demographics.
- Advertising or broker-review: none yet.
- Legal, tax, lending, or inspection advice: lending questions must be referred to lender.
- Privacy or sensitive data: basic lead data only.
```

## Example 2, Property Question

User request:

```text
Diana wants a quick read on 1200 Example St before she tells the buyers whether it is worth touring.
```

Orchestrator output:

```md
## Destination
`02_property_research/`

## Why This Folder
The team needs source-backed property and market context before drafting a client recommendation.

## What Not To Do Yet
Do not tell the client to tour or skip it until research is complete and Diana reviews the recommendation.
```

## Example 3, Accepted Offer

User request:

```text
Offer accepted. Option period ends Friday at 5 PM. Inspection is tomorrow.
```

Orchestrator output:

```md
## Destination
`04_transaction_coordinator/`

## Why This Folder
This is live contract work with deadlines and document tracking.

## Compliance Flags
- Deadline risk: verify all dates against the executed contract.
- Legal advice risk: do not interpret contract rights beyond the team checklist.
- Human review needed before adding deadlines to the official deal file.
```

