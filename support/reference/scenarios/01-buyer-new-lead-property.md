# Scenario 01: New Buyer Lead + Property Question

Standard new-buyer flow that asks about a specific property. Exercises three specialists in sequence.

## Raw Request

```text
Jordan is a new buyer lead relocating to Austin. Budget is 750k to 825k. Wants a three-bedroom home, outdoor space for a dog, and a manageable commute to downtown. Jordan asks whether 4812 Sample Bend is worth touring this weekend.
```

## Routing Decision (00_orchestrator)

Sequence: `01_lead_qualifier` → `02_property_research` → `03_client_communication`.

**Why.** This request combines a new lead, a property research question, and a client-facing reply. The team should qualify the lead enough to understand criteria, research the property before making claims, then draft the response.

**Compliance scan:**
- Fair housing: low, no protected-class request, keep location discussion objective.
- Advertising or broker-review: low, not public-facing.
- Legal, tax, lending, appraisal, or inspection advice: medium, financing belongs with lender.
- Privacy or sensitive data: low.
- Source reliability: medium, property status and claims need current approved source.
- Wire-fraud: not applicable.
- Buyer rep agreement: NOT confirmed — block any tour scheduling until verified.
- Language: English (default).

## Handoff Chain

Scenario packets are abbreviated for readability. In live use, add the shared metadata from `../handoff-contracts.md`, check output against `../agency-standard.md`, and update the lead/deal log for Deal Desk visibility.

### Packet 1: 00 → 01

```md
From: 00_orchestrator
To: 01_lead_qualifier
Matter ID: MOCK-BUYER-001
Stage: Lead intake
Client or lead: Jordan
Matter: New buyer lead asking about a specific property
Urgency: Medium, possible weekend tour
Current status: Unqualified lead with basic criteria

## Known Facts
- Relocating to Austin.
- Budget comfort is 750k to 825k.
- Wants three bedrooms.
- Wants outdoor space for a dog.
- Wants a manageable commute to downtown.
- Asked about 4812 Sample Bend.

## Missing Information
- Blocking: financing/pre-approval status, current agent relationship, buyer rep agreement status.
- Helpful: relocation timeline, commute tolerance, deal breakers.
- Can wait: showing windows.

## Compliance Flags
[as above]

## Requested Output
Lead summary, temperature, qualification questions, handoff packet for property research.
```

### Packet 2: 01 → 02

```md
From: 01_lead_qualifier
To: 02_property_research
Matter ID: MOCK-BUYER-001
Stage: Property research
Client or lead: Jordan
Matter: Evaluate whether 4812 Sample Bend should stay on the tour list
Urgency: Medium
Current status: Warm lead, research needed before client reply

## Known Facts
- Criteria: 3 bedrooms, outdoor space for dog, downtown commute, 750k-825k budget.
- Property address is mock.

## Missing Information
- Blocking: current listing status from approved source, verified property facts.
- Helpful: commute anchor, renovation/system-history docs.

## Compliance Flags
- Source reliability: high, status and condition claims are volatile.
- Professional advice: medium, condition claims require documentation.
- Buyer rep agreement: NOT confirmed (blocking for any tour proposal).

## Requested Output
Research brief with source-confidence labels and a client-ready takeaway.

## Lead Qualifier Output (added to packet)
- Lead Temperature: Warm
- Recommended next action: ask two qualification questions while research checks the property.
- Suggested questions: pre-approval status; current agent relationship.
```

### Packet 3: 02 → 03

```md
From: 02_property_research
To: 03_client_communication
Matter ID: MOCK-BUYER-001
Stage: Client communication
Client or lead: Jordan
Matter: Draft reply about whether to tour 4812 Sample Bend
Urgency: Medium
Current status: Research complete enough for cautious draft, facts still need Diana verification

## Known Facts
- Property appears aligned with several stated criteria.
- Current status and update claims need verification.

## Missing Information
- Blocking: Diana must verify status and rep agreement before any tour invite.
- Helpful: docs for renovation and HVAC.

## Compliance Flags
- Source reliability: high, caveat status and updates.
- Buyer rep agreement: must be signed before scheduling a tour. Reply must NOT propose a tour date yet.

## Source And Proof State
- Source of truth: team-approved MLS, not yet checked.
- Source checked at: pending.
- Needs recheck before: any tour invite.
- Proof available: none.
- Proof missing: current status, renovation docs.

## Requested Output
Draft buyer reply: acknowledge interest, ask qualification questions, do NOT promise availability, do NOT schedule tour, explain the buyer rep agreement requirement gently.

## Human Review
- Reviewer needed: Diana.
- Review reason: client-facing recommendation, unverified facts, rep-agreement gate.
- Cannot proceed until: status verified and rep agreement consult scheduled.
```

## Final Output (drafted by 03_client_communication)

**Draft Status:** Needs Diana review.

**Voice Score:** 18/20.

**Draft:**

> Subject: Quick read on 4812 Sample Bend
>
> Hi Jordan,
>
> Thanks for reaching out about 4812 Sample Bend. My read is it could fit what you're describing — three bedrooms, outdoor space, manageable downtown commute. Worth keeping in the mix.
>
> Before we lean on it too hard, I want to verify current status and a couple of the listing's claims. I'll have that confirmed by tomorrow.
>
> Two quick questions on your end:
>
> 1. Are you already pre-approved through a lender, or still sorting that out?
> 2. Are you working with another agent right now?
>
> One housekeeping note: before we tour any homes together, we sign a short buyer's representation agreement that explains how I work and how I get paid. It's a 15-minute conversation. Happy to do it by phone or video this week if it makes sense.
>
> Diana

**Human Review Notes:**
Diana should verify current property status, confirm Jordan has no existing agent, and offer the rep agreement consult before any tour. The draft does not promise availability and does not schedule a tour.

## What This Demonstrates

- **The orchestrator routes complex requests as sequences, not single-folder hands-offs.**
- **The compliance scan catches the buyer rep gate before a tour is offered.**
- **Source-of-truth fields prevent the system from claiming verified facts.**
- **Voice scoring + human review gates protect the client-facing draft.**
- **Each specialist does one job and passes a clean packet to the next.**
