# Examples

Use these examples to keep research concrete. The research desk does not decide for the client. It separates facts, signals, questions, confidence, and the next handoff.

## Example 1, Property Tour With Stale Status

Input:

```text
Jordan asks whether 4812 Sample Bend is worth touring this weekend. The only listing note is three days old and says active.
```

Output:

```md
## Research Brief

## Research Question
Should Diana prioritize this property for Jordan's weekend tour list?

## Property Snapshot
- Address: 4812 Sample Bend, synthetic.
- Status: stale note says active, but current status must be verified.
- Client criteria: 3 bedrooms, 750k to 825k, outdoor space, manageable commute to downtown.

## Facts, Signals, Questions
- Fact: A three-day-old internal note says active. Source: mock listing note, checked three days ago.
- Signal: The property may match several client criteria, but status and condition are not current enough for a recommendation.
- Question: Is it still active in the approved team source?
- Question: Are any claimed updates supported by disclosure, permit, or seller-side documentation?

## Confidence And Usability Labels
- Overall confidence: Medium for internal triage.
- Current availability: Do not use yet.
- Tour recommendation: Needs Diana verification.
- Client-ready takeaway: Can share only with status caveat.

## Handoff Packet
From: `02_property_research`
To: `03_client_communication`
Matter ID: `MOCK-BUYER-001`
Stage: Research to client communication
Client or lead: Jordan
Matter: Cautious property-tour reply
Urgency: Medium
Current status: Research complete enough for a caveated draft, current status not verified

## Known Facts
- A stale internal note says the property was active three days ago.
- The property appears to match bedroom, budget, and outdoor-space criteria on paper.
- Current availability is not verified.

## Missing Information
- Blocking:
  - Current status from approved source.
- Helpful:
  - Documentation for claimed updates.
  - Commute source.
- Can wait:
  - Final tour time.

## Compliance Flags
- Fair housing: low, avoid neighborhood suitability claims.
- Advertising or broker-review: low, one-to-one client reply.
- Legal, tax, lending, appraisal, or inspection advice: medium, do not advise condition or value.
- Privacy or sensitive data: low.
- Source reliability: high, listing status is stale.
- Wire fraud: not applicable.
- Buyer rep agreement: verify before showing.
- Language: unknown.

## Source And Proof State
- Source of truth: team-approved MLS or brokerage source needed.
- Source checked at: stale mock note, three days ago.
- Needs recheck before: any client-facing availability statement.
- Proof available: old internal note.
- Proof missing: current status.

## Requested Output
Draft a short client reply that says the property may be worth checking, but current status must be verified before recommending a tour.

## Next Owner
`03_client_communication`

## Human Review
- Reviewer needed: Diana or assigned agent.
- Review reason: client-facing recommendation with volatile property facts.
- Cannot proceed until: status is verified or the draft keeps the status caveat.

## Human Review Needed Before
- sending to a client
- relying on a source
- requesting a showing
```

## Example 2, Fair-Housing-Sensitive Neighborhood Question

Input:

```text
Buyer asks: "Can you find us a safe, family-friendly neighborhood with people like us?"
```

Output:

```md
## Research Brief

## Research Question
How can Diana respond with objective location research without steering or protected-class assumptions?

## Compliance Note
Do not answer with safety, family-suitability, demographic, or "people like us" conclusions.

## Objective Criteria To Offer
- Commute time.
- Budget.
- Home size.
- Parks or trails.
- School-boundary lookup if the client requests school information.
- Traffic, transit, walkability, or noise.
- Public incident-data resources, with source limits.

## Confidence And Usability Labels
- Overall confidence: High for compliance-safe reframe.
- Public incident data: Needs client review and source caveat.
- School boundaries: Needs official district lookup and recheck.

## Handoff Packet
From: `02_property_research`
To: `03_client_communication`
Matter ID: `MOCK-FAIR-HOUSING-001`
Stage: Research to client communication
Client or lead: Buyer lead
Matter: Compliant neighborhood research reframe
Urgency: Medium
Current status: Safe response direction ready

## Known Facts
- Client asked for safety and family-suitability conclusions.
- The team should not make demographic, safety, or protected-class suitability claims.
- Objective criteria can be offered instead.

## Missing Information
- Blocking:
  - Diana must approve the fair-housing-safe phrasing.
- Helpful:
  - Which objective criteria matter most to the client.
  - Exact commute destination and travel mode.
- Can wait:
  - Specific property shortlist.

## Compliance Flags
- Fair housing: high, reframe to objective criteria.
- Advertising or broker-review: medium, use neutral educational wording.
- Legal, tax, lending, appraisal, or inspection advice: low.
- Privacy or sensitive data: low.
- Source reliability: medium, any source links need date and limits.
- Wire fraud: not applicable.
- Buyer rep agreement: not relevant to this question.
- Language: unknown.

## Source And Proof State
- Source of truth: official public-source menu and client-defined criteria, not agent opinion.
- Source checked at: current chat, no live lookup.
- Needs recheck before: sending any source link or quoting a boundary result.
- Proof available: client's wording.
- Proof missing: client's objective criteria.

## Requested Output
Draft a compliant response that avoids ranking neighborhoods and asks the client which objective criteria they want compared.

## Next Owner
`03_client_communication`

## Human Review
- Reviewer needed: Diana or broker if unsure.
- Review reason: fair-housing-sensitive client request.
- Cannot proceed until: protected-class and safety conclusions are removed.

## Human Review Needed Before
- sending to a client
- making any neighborhood comparison
```

## Example 3, Conflicting Permit Signals

Input:

```text
Mock listing sheet says the kitchen renovation was fully permitted. Mock city permit summary shows no matching kitchen permit found.
```

Output:

```md
## Research Brief

## Research Question
How should Diana handle a listing claim that conflicts with a public permit search?

## Facts, Signals, Questions
- Fact: Listing sheet claims kitchen renovation was fully permitted. Source: mock listing sheet, checked today.
- Fact: Mock city permit summary did not show a matching kitchen permit. Source: mock city permit search, checked today.
- Signal: The sources conflict or the permit search may be incomplete.
- Question: Can the listing side provide permit numbers, invoices, or clarification?
- Question: Should inspector or specialist review the renovation details?

## Confidence And Usability Labels
- Listing permit claim: Needs Diana verification.
- Permit search result: Internal only, limited source.
- Client-ready conclusion: Do not use yet.

## Handoff Packet
From: `02_property_research`
To: `04_transaction_coordinator`
Matter ID: `MOCK-PERMIT-001`
Stage: Deal task or pre-offer follow-up
Client or lead: Buyer client
Matter: Permit verification follow-up
Urgency: Medium
Current status: Conflicting source signals

## Known Facts
- Listing sheet claims a fully permitted kitchen renovation.
- Public permit search did not clearly confirm the same claim.
- The conflict may matter if the buyer relies on renovation status.

## Missing Information
- Blocking:
  - Permit number or seller-side documentation if this affects offer strategy.
- Helpful:
  - Seller disclosure.
  - Inspector comments.
- Can wait:
  - Contractor opinion unless buyer proceeds.

## Compliance Flags
- Fair housing: not applicable.
- Advertising or broker-review: low.
- Legal, tax, lending, appraisal, or inspection advice: medium, do not conclude legality or condition.
- Privacy or sensitive data: low.
- Source reliability: high, sources conflict.
- Wire fraud: not applicable.
- Buyer rep agreement: not relevant to this question.
- Language: unknown.

## Source And Proof State
- Source of truth: city permit record plus seller/listing-side documentation.
- Source checked at: today, mock data.
- Needs recheck before: client relies on renovation claim.
- Proof available: listing claim and limited permit search.
- Proof missing: direct permit confirmation.

## Requested Output
Track the permit-verification task and decide whether this creates a deal task, inspection question, or seller-side follow-up.

## Next Owner
`04_transaction_coordinator`

## Human Review
- Reviewer needed: Diana or assigned agent.
- Review reason: conflicting property condition/source claim.
- Cannot proceed until: claim is caveated or verified.

## Human Review Needed Before
- relying on a source
- sending to a client
- adding to a live transaction file
```
