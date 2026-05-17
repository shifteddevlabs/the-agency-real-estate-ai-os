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
- Client criteria: 3 bedrooms, 750k to 825k, outdoor space for dog, manageable commute to downtown.

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

## Client-Ready Takeaway
"This one may be worth keeping in the mix if the commute and yard work for you, but I want to verify current status before we count on it for the weekend."

## Handoff Packet
From: `02_property_research`
To: `03_client_communication`
Matter ID: `MOCK-BUYER-001`
Stage: Client communication
Client or lead: Jordan
Matter: Cautious property-tour reply
Urgency: Medium
Current status: Research complete enough for a caveated draft

## Missing Information
- Blocking:
  - Current status from approved source.
- Helpful:
  - Documentation for claimed updates.
- Can wait:
  - Final tour time.

## Source And Proof State
- Source of truth: team-approved MLS or brokerage source needed.
- Source checked at: stale mock note, three days ago.
- Needs recheck before: any client-facing availability statement.
- Proof available: old internal note.
- Proof missing: current status.

## Human Review
- Reviewer needed: Diana or assigned agent.
- Review reason: client-facing recommendation with volatile property facts.
- Cannot proceed until: status is verified or the draft keeps the status caveat.
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

## Client-Ready Takeaway
"I can't choose a neighborhood for you based on family status or make a blanket safety claim, but I can help you compare areas using objective criteria: commute, budget, home style, parks, school-boundary resources if that matters to you, traffic, transit, and public data sources you can review."

## Handoff Packet
From: `02_property_research`
To: `03_client_communication`
Matter ID: `MOCK-FAIR-HOUSING-001`
Stage: Client communication
Client or lead: Buyer lead
Matter: Compliant neighborhood research reframe
Urgency: Medium
Current status: Safe response direction ready

## Compliance Flags
- Fair housing: high, client used family and affinity language, reframe to objective criteria.
- Source reliability: medium, any data source offered must include date and limits.

## Human Review
- Reviewer needed: Diana or broker if unsure.
- Review reason: fair-housing-sensitive client request.
- Cannot proceed until: protected-class language is removed from draft.
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

## Client-Ready Takeaway
"The listing notes say the kitchen work was permitted. I want to verify that before we rely on it, because the first public-record check did not clearly confirm the same thing."

## Handoff Packet
From: `02_property_research`
To: `04_transaction_coordinator`
Matter ID: `MOCK-PERMIT-001`
Stage: Deal task or pre-offer follow-up
Client or lead: Buyer client
Matter: Permit verification follow-up
Urgency: Medium
Current status: Conflicting source signals

## Missing Information
- Blocking:
  - Permit number or seller-side documentation if this affects offer strategy.
- Helpful:
  - Seller disclosure.
  - Inspector comments.
- Can wait:
  - Contractor opinion unless buyer proceeds.

## Source And Proof State
- Source of truth: city permit record plus seller/listing-side documentation.
- Source checked at: today, mock data.
- Needs recheck before: client relies on renovation claim.
- Proof available: listing claim and limited permit search.
- Proof missing: direct permit confirmation.

## Human Review
- Reviewer needed: Diana or assigned agent.
- Review reason: conflicting property condition/source claim.
- Cannot proceed until: claim is caveated or verified.
```

