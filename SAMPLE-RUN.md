# Sample Run

This mock run shows how a single request moves through The Agency. It uses synthetic data only.

## Raw Request

```text
Jordan is a new buyer lead relocating to Austin. Budget is 750k to 825k. Wants a three-bedroom home, outdoor space for a dog, and a manageable commute to downtown. Jordan asks whether 4812 Sample Bend is worth touring this weekend.
```

## 00 Orchestrator

### Routing Decision

Sequence:

1. `01_lead_qualifier/`
2. `02_property_research/`
3. `03_client_communication/`

### Why

This request combines a new lead, a property research question, and a client-facing reply. The team should qualify the lead enough to understand criteria, research the property before making claims, then draft the response.

### Handoff Packet

From: `00_orchestrator`
To: `01_lead_qualifier`
Matter ID: `MOCK-BUYER-001`
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

- Blocking:
  - Financing or pre-approval status.
  - Current agent relationship.
- Helpful:
  - Exact relocation timeline.
  - Commute tolerance in minutes.
  - Deal breakers.
- Can wait:
  - Preferred showing windows after the first reply.

## Compliance Flags

- Fair housing: low, no protected-class request yet, keep location discussion objective.
- Advertising or broker-review: low, not public-facing.
- Legal, tax, lending, appraisal, or inspection advice: medium, financing belongs with lender.
- Privacy or sensitive data: low, basic lead data only.
- Source reliability: medium, property status and claims need current approved source.

## 01 Lead Qualifier

### Output

Lead Temperature: Warm

Recommended next action: ask two qualification questions while research checks the property.

Suggested questions:

- Are you already pre-approved or still choosing a lender?
- Are you currently working with another agent?

### Handoff Packet

From: `01_lead_qualifier`
To: `02_property_research`
Matter ID: `MOCK-BUYER-001`
Stage: Property research
Client or lead: Jordan
Matter: Evaluate whether 4812 Sample Bend should stay on the tour list
Urgency: Medium
Current status: Warm lead, research needed before client reply

## Known Facts

- Criteria: 3 bedrooms, outdoor space for dog, downtown commute, 750k to 825k budget.
- The property address is mock data.

## Missing Information

- Blocking:
  - Current listing status from approved source.
  - Verified property facts from team-provided listing sheet or approved source.
- Helpful:
  - Commute anchor and max commute time.
  - Renovation or system-history documentation if listing claims updates.
- Can wait:
  - Showing time preference.

## Compliance Flags

- Source reliability: high, property status and condition claims are volatile.
- Professional advice: medium, condition and repair claims require documentation or professional review.

## 02 Property Research

### Research Brief

Research Question: Should Diana prioritize this property for Jordan's weekend tour list?

Property Snapshot:

- Address: 4812 Sample Bend, synthetic.
- Status: must be verified before recommending a tour.
- Claimed updates: synthetic kitchen renovation and newer HVAC, both unverified.

Market Context:

- Use team-approved MLS or brokerage source for price, status, and comps.
- Use public records only as supporting context, not as a replacement for MLS.

Risks And Follow-Up Questions:

- Verify current status.
- Ask for support on kitchen renovation and HVAC age.
- Confirm commute and yard expectations with Jordan.

Client-Ready Takeaway:

```text
This one may be worth keeping in the mix if the commute and yard work for Jordan in person. Before we lean too hard on it, we should verify current status and support for the claimed updates.
```

Confidence And Usability Labels:

- Overall confidence: Medium, useful for internal triage only.
- Current status: Do not use yet until rechecked.
- Claimed updates: Needs Diana verification.
- Client-ready takeaway: Can share after Diana reviews.

### Handoff Packet

From: `02_property_research`
To: `03_client_communication`
Matter ID: `MOCK-BUYER-001`
Stage: Client communication
Client or lead: Jordan
Matter: Draft reply about whether to tour 4812 Sample Bend
Urgency: Medium
Current status: Research complete enough for cautious draft, facts still need Diana verification

## Known Facts

- The property appears aligned with several stated criteria in the mock scenario.
- Current status and update claims need verification.

## Missing Information

- Blocking:
  - Diana must verify status before sending.
- Helpful:
  - Documentation for renovation and HVAC.
- Can wait:
  - Exact tour time.

## Compliance Flags

- Source reliability: high, caveat status and updates.
- Legal, tax, lending, appraisal, or inspection advice: low if draft avoids condition claims.

## Human Review

- Reviewer needed: Diana or assigned agent.
- Review reason: client-facing recommendation and unverified property facts.
- Cannot proceed until: status caveat is checked or retained.

## 03 Client Communication

### Draft Status

Needs Diana review.

### Draft

Subject: Quick read on 4812 Sample Bend

Hi Jordan,

My read is that 4812 Sample Bend is worth keeping in the mix for now, especially if the commute and yard feel right to you in person.

The main thing I do not want to overstate yet is condition. The listing notes mention updates, and I would like to verify those details before we rely on them too heavily.

The next clean step is to confirm current availability, ask for any support on the updates, and then decide whether it earns a spot on the tour list.

Diana

### Voice Score

18/20

### Human Review Notes

Diana should verify current status and decide whether the cautious recommendation matches her read before sending.

