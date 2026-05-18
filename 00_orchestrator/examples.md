# Examples

These examples show the orchestrator doing only its job: classify, scan risk, choose the next owner, and create a complete handoff packet. It does not perform specialist work.

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
The next job is to qualify intent, financing, representation status, and missing criteria before research or drafting.

## Handoff Packet
From: `00_orchestrator`
To: `01_lead_qualifier`
Matter ID: `MOCK-BUYER-001`
Stage: Intake
Client or lead: Alex
Matter: New buyer inquiry from Zillow
Urgency: Medium
Current status: Unqualified lead with partial criteria

## Known Facts
- Alex wants to buy in Austin.
- Budget mentioned: under 800k.
- Possible area interest: East Austin.
- Timeline: around 90 days.

## Missing Information
- Blocking:
  - Current agent relationship.
  - Buyer representation agreement status.
  - Contact preference.
- Helpful:
  - Financing or pre-approval status.
  - Must-haves and deal breakers.
  - Preferred language.
- Can wait:
  - Showing windows.

## Compliance Flags
- Fair housing: low, avoid steering or demographic assumptions.
- Advertising or broker-review: low, one-to-one intake.
- Legal, tax, lending, appraisal, or inspection advice: medium, financing questions route to lender.
- Privacy or sensitive data: low, use only submitted lead data.
- Source reliability: medium, portal lead details need confirmation.
- Wire fraud: not applicable.
- Buyer rep agreement: required before any showing.
- Language: unknown, capture preference.

## Source And Proof State
- Source of truth: pasted Zillow lead text.
- Source checked at: current chat.
- Needs recheck before: any property recommendation or showing discussion.
- Proof available: lead message.
- Proof missing: representation status, financing status, contact preference.

## Requested Output
Qualify Alex, list missing information, recommend next action, and prepare a handoff to client communication if a first reply is needed.

## Next Owner
`01_lead_qualifier`

## Human Review
- Reviewer needed: Diana or assigned agent.
- Review reason: first client-facing buyer reply.
- Cannot proceed until: buyer rep status is known or the reply offers a consult instead of a showing.

## Human Review Needed Before
- sending to a client
- proposing a showing
- relying on portal data

## What Not To Do Yet
Do not offer a showing, recommend a neighborhood, or promise availability.
```

## Example 2, Property Question

User request:

```text
Diana wants a quick read on 1200 Example St before she tells the buyers whether it is worth touring.
```

Orchestrator output:

```md
## Routing Summary
This is a property research request that needs source-backed facts before any client recommendation.

## Destination
`02_property_research/`

## Why This Folder
The team needs property, source, and confidence context before drafting a client-facing read.

## Handoff Packet
From: `00_orchestrator`
To: `02_property_research`
Matter ID: `MOCK-PROPERTY-001`
Stage: Property research
Client or lead: Buyer client
Matter: Quick read on 1200 Example St
Urgency: Medium
Current status: Research needed before client recommendation

## Known Facts
- Diana wants a quick read before advising buyers.
- Address: 1200 Example St.
- The requested output may become client-facing.

## Missing Information
- Blocking:
  - Current property status from approved source.
  - Client criteria.
  - Buyer rep agreement status if a showing is being considered.
- Helpful:
  - Listing sheet or MLS export.
  - Seller disclosure or permit notes.
- Can wait:
  - Full comp package.

## Compliance Flags
- Fair housing: low, avoid neighborhood suitability claims.
- Advertising or broker-review: low unless public copy is produced.
- Legal, tax, lending, appraisal, or inspection advice: medium, do not advise value or condition.
- Privacy or sensitive data: low.
- Source reliability: high, property status is volatile.
- Wire fraud: not applicable.
- Buyer rep agreement: verify before any tour recommendation.
- Language: unknown.

## Source And Proof State
- Source of truth: approved team MLS or brokerage source, not yet provided.
- Source checked at: not checked.
- Needs recheck before: any client-facing property status or tour recommendation.
- Proof available: address only.
- Proof missing: live status, client criteria, source documents.

## Requested Output
Create a research brief that separates facts, signals, questions, and recommendation caveats.

## Next Owner
`02_property_research`

## Human Review
- Reviewer needed: Diana.
- Review reason: property recommendation may affect client action.
- Cannot proceed until: current status and source limits are clear.

## Human Review Needed Before
- sending to a client
- recommending a tour
- relying on a source

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
## Routing Summary
This is live contract work with deadlines and document tracking.

## Destination
`04_transaction_coordinator/`

## Why This Folder
The request involves option-period timing, inspection coordination, and contract-source verification.

## Handoff Packet
From: `00_orchestrator`
To: `04_transaction_coordinator`
Matter ID: `MOCK-TX-OPTION-001`
Stage: Early option period
Client or lead: Buyer client
Matter: Accepted offer, option and inspection tracking
Urgency: High
Current status: Offer accepted, dates unverified

## Known Facts
- Offer accepted.
- User says option period ends Friday at 5 PM.
- User says inspection is tomorrow.

## Missing Information
- Blocking:
  - Executed contract.
  - Effective date.
  - Inspector confirmation.
- Helpful:
  - Title receipt for earnest money and option fee.
  - Financing addendum status.
- Can wait:
  - Closing-week logistics.

## Compliance Flags
- Fair housing: not applicable.
- Advertising or broker-review: not applicable.
- Legal, tax, lending, appraisal, or inspection advice: high, do not interpret rights beyond checklist.
- Privacy or sensitive data: medium, keep deal details limited.
- Source reliability: high, all dates must be verified against executed contract.
- Wire fraud: not applicable.
- Buyer rep agreement: should already be on file, confirm.
- Language: unknown.

## Source And Proof State
- Source of truth: executed contract, not provided.
- Source checked at: not checked.
- Needs recheck before: adding deadlines to deal file or drafting client update.
- Proof available: user note only.
- Proof missing: executed contract and inspection confirmation.

## Requested Output
Create an option-period checklist with verified vs unverified dates, blockers, escalations, and client update points.

## Next Owner
`04_transaction_coordinator`

## Human Review
- Reviewer needed: Diana or assigned agent.
- Review reason: contract deadlines are unverified and time-sensitive.
- Cannot proceed until: dates are checked against the executed contract or clearly labeled unverified.

## Human Review Needed Before
- changing a deadline
- sending to a client
- adding to a live transaction file

## What Not To Do Yet
Do not treat Friday at 5 PM as final until verified against the executed contract.
```
