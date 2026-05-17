# Research Handoff Examples

These are synthetic examples for practicing `02_property_research/` handoffs. They use the V2 handoff packet fields and avoid real client, property, MLS, or transaction data.

## V2 Packet Fields Used

Each example includes:

- `From`
- `To`
- `Matter ID`
- `Stage`
- `Client or lead`
- `Matter`
- `Urgency`
- `Current status`
- `Known Facts`
- `Missing Information`, split into `Blocking`, `Helpful`, and `Can wait`
- `Compliance Flags`, with required action
- `Source And Proof State`
- `Decision Trail`
- `Requested Output`
- `Next Owner`
- `Human Review`
- `Human Review Needed Before`

## Example 1, Austin Buyer Stale Status

### Input

```text
Synthetic buyer Jordan wants to know whether to tour 9100 Example Hollow in Austin this weekend.
The team has a mock MLS export from three days ago that says Active.
Budget is 775k, wants 3 bedrooms, outdoor space, and a reasonable downtown commute.
```

### Research Brief

#### Research Question

Is the fictional Austin property still viable enough to draft a client reply about touring?

#### Facts

- Fact: The only property-status source in the packet is a mock team MLS export dated 2026-05-09.
- Fact: The mock MLS export says `Active`, 3 bedrooms, 2 baths, and list price 759000.
- Fact: The mock client criteria are 3 bedrooms, outdoor space, and under 800000.

#### Signals

- Signal: The property appears aligned with price and bedroom criteria based on the stale export.
- Signal: Weekend tour viability is uncertain because status can change quickly.

#### Questions

- Question: Has the property gone pending, under contract, withdrawn, or changed showing availability since 2026-05-09?
- Question: Does Diana want commute and outdoor-space claims verified before the client reply?

#### Recommendation

- Recommendation: Do not tell the client the property is available until Diana or the team checks the live brokerage-approved source.
- Recommendation: Send to `03_client_communication/` only for a cautious draft that says the team is rechecking availability.

#### Sources Checked

- Source: Mock Team MLS Export
- URL or internal document: synthetic-file://mock-mls-export-9100-example-hollow
- Date checked: 2026-05-09 17:05 CT
- What it supports: old listing status, price, bed/bath count, and basic listing details.
- Limits or warnings: stale for tour scheduling and cannot prove current availability on 2026-05-12.

#### Confidence And Usability Labels

- Overall confidence: Medium for internal triage, Low for current availability.
- Status claim: Do not use yet.
- Price and bedroom fit: Needs Diana verification.
- Client-ready takeaway: Can share only with a recheck caveat.

### Handoff Packet V2

```md
## Handoff Packet

From: `02_property_research`
To: `03_client_communication`
Matter ID: `MOCK-AUS-BUYER-STALE-001`
Stage: Research to client communication
Client or lead: Jordan, synthetic buyer
Matter: Cautious client reply about 9100 Example Hollow tour interest
Urgency: High, buyer asked about this weekend
Current status: Research complete for triage, current listing status not verified

## Known Facts

- The only available property-status source is a mock MLS export checked on 2026-05-09.
- The stale source lists the fictional property as Active at 759000 with 3 bedrooms and 2 baths.
- The property appears to match the synthetic buyer's price and bedroom criteria on paper.

## Missing Information

- Blocking:
  - Live brokerage-approved status as of 2026-05-12.
  - Showing availability for the requested weekend.
- Helpful:
  - Commute estimate source and date checked.
  - Confirmation of usable outdoor space from permitted source or showing notes.
- Can wait:
  - Detailed comp review.
  - Renovation-document review.

## Compliance Flags

- Source reliability: Required action, keep a clear stale-status caveat and recheck before sending.
- Advertising or broker-review: Required action, do not reuse listing language beyond verified factual basics.
- Fair housing: Required action, avoid neighborhood desirability claims.
- Legal, tax, lending, or inspection advice: Required action, do not discuss condition or value beyond sourced facts.
- Privacy or sensitive data: Required action, no personal financial details in downstream draft.

## Source And Proof State

- Source of truth: Live brokerage-approved listing source, not yet checked.
- Source checked at: Mock MLS export checked 2026-05-09 17:05 CT.
- Needs recheck before: Any client message that implies availability or any showing request.
- Recheck date: 2026-05-12, before client send.
- Proof available: stale mock MLS export.
- Proof missing: live status screenshot or team confirmation, showing instructions, commute source.

## Decision Trail

- Research found a likely criteria match but the status source is stale.
- Because availability is material and volatile, the recommendation is to draft only with a recheck caveat.
- Next folder is communication because the client needs a reply, not a final property recommendation.

## Requested Output

Draft a short client reply that says the property looks worth checking on paper, but the team is confirming current availability before recommending a tour slot.

## Next Owner

`03_client_communication`

## Human Review

- Reviewer needed: Diana or assigned agent.
- Review reason: client-facing tour guidance depends on current status.
- Cannot proceed until: live status is checked or the draft clearly says the team is checking it now.

## Human Review Needed Before

- sending to a client
- relying on a source
- requesting a showing
```

### Rubric Score Notes

| Rubric | Score | Notes |
|---|---:|---|
| Research | 92/100 | Strong question, source date, fact/signal/question split, and usability labels. Loses points because the example intentionally has stale status and limited source depth. |
| Handoff | 96/100 | Next owner, missing information, compliance flags, requested output, and human gate are explicit. Minor loss because commute and outdoor-space proof remain unresolved. |

## Example 2, Fair-Housing-Sensitive Neighborhood Question

### Input

```text
Synthetic relocation buyer Maya asks:
"Is North Loop better and safer for families than East Riverside?"
Budget is 650k. She wants to compare areas before flying to Austin.
```

### Research Brief

#### Research Question

How should the research desk handle a neighborhood comparison request that uses safety and family suitability language?

#### Facts

- Fact: The client is asking for neighborhood comparison, safety, and family suitability.
- Fact: Safety and family suitability can create fair-housing and steering risk if the team gives a conclusion.
- Fact: Objective public sources can be offered for the client to review directly.

#### Signals

- Signal: The client likely needs a decision framework, not a neighborhood ranking.
- Signal: A compliant answer can compare objective factors such as commute, listed inventory, property type, floodplain checks, public amenities, and official school-boundary lookup links.

#### Questions

- Question: Which objective criteria matter most to Maya, commute time, housing type, budget fit, transit, parks, or school-boundary lookup?
- Question: Does Diana want to provide a source menu and invite Maya to choose what to compare?

#### Recommendation

- Recommendation: Do not rank neighborhoods as safer, better, family-friendly, or unsuitable.
- Recommendation: Route to `03_client_communication/` for a reframe that offers objective source categories and asks Maya to choose practical criteria.

#### Sources Checked

- Source: Mock City Open Data Source Menu
- URL or internal document: synthetic-file://austin-objective-source-menu
- Date checked: 2026-05-12 09:20 CT
- What it supports: possible objective categories such as commute, transit, parks, floodplain, permit activity, and public service maps.
- Limits or warnings: does not support client-specific safety conclusions or protected-class suitability claims.

- Source: Mock School Boundary Lookup
- URL or internal document: synthetic-file://school-boundary-lookup
- Date checked: 2026-05-12 09:22 CT
- What it supports: boundary lookup process.
- Limits or warnings: boundaries can change and must be verified by the district or official tool.

#### Confidence And Usability Labels

- Overall confidence: High for compliance reframe, Medium for source menu.
- Neighborhood ranking: Do not use yet.
- Objective criteria menu: Can share with client.
- School-boundary details: Needs Diana verification and official lookup caveat.

### Handoff Packet V2

```md
## Handoff Packet

From: `02_property_research`
To: `03_client_communication`
Matter ID: `MOCK-AUS-FH-NEIGHBORHOOD-002`
Stage: Research to client communication
Client or lead: Maya, synthetic relocation buyer
Matter: Fair-housing-safe response to neighborhood comparison question
Urgency: Medium
Current status: Research complete for compliant reframe, no neighborhood ranking provided

## Known Facts

- The client's wording asks whether one area is better and safer for families than another.
- The team should not answer with a safety, demographic, or family-suitability conclusion.
- The team can offer objective criteria and official data sources for the client to review.

## Missing Information

- Blocking:
  - Diana must approve the fair-housing-safe phrasing before any client send.
- Helpful:
  - Maya's preferred objective criteria for comparison.
  - Exact commute destination and preferred travel mode.
  - Whether school-boundary lookup matters to Maya.
- Can wait:
  - Specific property shortlist.
  - Tour schedule.

## Compliance Flags

- Fair housing: Required action, do not rank areas by safety, family suitability, demographics, or protected-class proxies.
- Source reliability: Required action, cite only objective public-source categories and include date checked.
- Advertising or broker-review: Required action, keep response educational and neutral.
- Legal, tax, lending, or inspection advice: Required action, none expected, avoid advice beyond source navigation.
- Privacy or sensitive data: Required action, do not include family details beyond what is needed for the reply.

## Source And Proof State

- Source of truth: Objective public-source menu and official lookup tools, not agent opinion.
- Source checked at: 2026-05-12 09:20 CT and 2026-05-12 09:22 CT.
- Needs recheck before: Sending any source link or quoting a boundary result.
- Recheck date: same day as client send if links or boundaries are included.
- Proof available: synthetic objective-source menu and mock boundary lookup process.
- Proof missing: client's chosen criteria, official current boundary result, exact commute destination.

## Decision Trail

- Research identified fair-housing risk in the requested wording.
- Research converted the request into objective comparison categories.
- Next folder is communication because the needed deliverable is a client-safe reframe.

## Requested Output

Draft a response that thanks Maya, avoids ranking neighborhoods, offers objective categories the team can compare, and asks her to choose which criteria matter most.

## Next Owner

`03_client_communication`

## Human Review

- Reviewer needed: Diana or broker-designated reviewer.
- Review reason: fair-housing-sensitive wording.
- Cannot proceed until: the draft removes safety and family-suitability conclusions.

## Human Review Needed Before

- sending to a client
- relying on a source
- making any neighborhood comparison
```

### Rubric Score Notes

| Rubric | Score | Notes |
|---|---:|---|
| Research | 98/100 | Clearly defines the risk, avoids steering, separates objective sources from conclusions, and gives a usable communication handoff. Minor loss because exact client criteria are still missing. |
| Handoff | 98/100 | Compliance flag and required action are highly specific. Human review and "cannot proceed until" are clear. Minor loss because downstream source links remain synthetic placeholders. |

## Example 3, Accepted Offer Research To Transaction Handoff

### Input

```text
Synthetic buyer Alex has an accepted offer on 4400 Sample Oak Court in Austin.
The team wants research moved into transaction coordination.
Mock notes say the option period ends Friday at 5 PM, inspection is scheduled tomorrow, and the buyer asked whether old permits or floodplain records create next steps.
```

### Research Brief

#### Research Question

What research findings and proof gaps need to move from property research into the live transaction checklist?

#### Facts

- Fact: The matter is now an accepted-offer workflow in this synthetic scenario.
- Fact: Mock transaction notes say option period ends Friday at 5 PM, but no executed contract proof is attached in the research packet.
- Fact: A mock city permit search found a 2017 water-heater permit marked finaled.
- Fact: A mock floodplain lookup did not show the parcel inside the reviewed floodplain layer, but the source is not a substitute for insurance, survey, lender, or title guidance.

#### Signals

- Signal: Permit and floodplain research create transaction follow-up tasks, not client advice.
- Signal: The option-period date is urgent but must be verified against the executed contract.

#### Questions

- Question: Is the executed contract available and do the deadline fields confirm Friday at 5 PM?
- Question: Should the inspection report ask the inspector to note water-heater age, installation, and any visible drainage issues?
- Question: Does title, lender, or insurance need to confirm flood-related requirements?

#### Recommendation

- Recommendation: Hand off to `04_transaction_coordinator/` with tasks, owners, proof gaps, and urgency.
- Recommendation: Do not tell the client permits or floodplain items are "clear"; say the team is tracking them and will verify through the proper sources.

#### Sources Checked

- Source: Mock City Permit Portal
- URL or internal document: synthetic-file://city-permit-4400-sample-oak
- Date checked: 2026-05-12 10:10 CT
- What it supports: one synthetic 2017 water-heater permit marked finaled.
- Limits or warnings: does not prove all work was permitted or property condition is acceptable.

- Source: Mock Floodplain Map Review
- URL or internal document: synthetic-file://floodplain-review-4400-sample-oak
- Date checked: 2026-05-12 10:18 CT
- What it supports: no reviewed layer match in the synthetic lookup.
- Limits or warnings: not a substitute for survey, insurance, lender, title, or professional flood determination.

- Source: Mock Transaction Note
- URL or internal document: synthetic-file://accepted-offer-note-alex
- Date checked: 2026-05-12 10:00 CT
- What it supports: accepted-offer status, claimed option deadline, and inspection timing.
- Limits or warnings: not executed contract proof.

#### Confidence And Usability Labels

- Overall confidence: Medium.
- Accepted-offer status: Needs Diana verification.
- Option deadline: Do not use yet until contract proof is checked.
- Permit record: Can share internally, needs Diana verification before client summary.
- Floodplain lookup: Needs professional review before any client reliance.

### Handoff Packet V2

```md
## Handoff Packet

From: `02_property_research`
To: `04_transaction_coordinator`
Matter ID: `MOCK-AUS-TXN-003`
Stage: Research to transaction coordination
Client or lead: Alex, synthetic buyer
Matter: Accepted-offer research findings for 4400 Sample Oak Court
Urgency: High, claimed option deadline is Friday at 5 PM
Current status: Research has produced transaction tasks, deadline proof still missing

## Known Facts

- Mock notes say the offer is accepted and inspection is scheduled tomorrow.
- Mock notes say the option period ends Friday at 5 PM, but the executed contract is not in the research packet.
- Mock city permit search found one 2017 water-heater permit marked finaled.
- Mock floodplain lookup did not show a reviewed layer match for the fictional parcel.

## Missing Information

- Blocking:
  - Executed contract deadline proof.
  - Inspection appointment confirmation.
  - Seller disclosure packet status.
- Helpful:
  - Title, lender, or insurance guidance on flood-related requirements.
  - Inspector notes on water heater, drainage, and any visible permit-related concerns.
  - HOA or survey documents if applicable.
- Can wait:
  - Client-friendly summary after Diana reviews proof.
  - Longer market context after option-period tasks are stable.

## Compliance Flags

- Legal or contract advice: Required action, do not interpret contract deadlines without Diana/broker review and executed contract proof.
- Inspection advice: Required action, do not estimate repair costs or condition from permit data.
- Source reliability: Required action, mark permit and floodplain findings as research leads, not final conclusions.
- Privacy or sensitive data: Required action, keep transaction documents in the approved file system only.
- Fair housing: Required action, no neighborhood suitability claims needed or allowed.

## Source And Proof State

- Source of truth: Executed contract for deadlines, inspection confirmation for appointment, official permit portal for permit lead, professional/title/lender sources for flood-related reliance.
- Source checked at: 2026-05-12 10:00 CT, 10:10 CT, and 10:18 CT.
- Needs recheck before: Any deadline update, repair request strategy, or client-facing transaction summary.
- Recheck date: 2026-05-12, immediately after executed contract is available.
- Proof available: mock transaction note, mock permit search, mock floodplain lookup.
- Proof missing: executed contract, inspection confirmation, seller disclosure, professional flood guidance if needed.

## Decision Trail

- Research found items that now create checklist tasks inside a live deal.
- Because the matter is accepted-offer stage, the next owner should be transaction coordination, not client communication first.
- Communication should wait until transaction coordinator verifies deadlines and Diana reviews the client-safe summary.

## Requested Output

Create a transaction checklist that verifies deadlines, tracks inspection and disclosure proof, preserves permit and floodplain research as follow-up items, and marks what Diana must review before the client update.

## Next Owner

`04_transaction_coordinator`

## Human Review

- Reviewer needed: Diana, plus broker or transaction lead if deadline proof conflicts.
- Review reason: live transaction deadline and professional-advice risk.
- Cannot proceed until: executed contract deadline is verified and missing proof is logged.

## Human Review Needed Before

- changing a deadline
- relying on a source
- adding to a live transaction file
- sending to a client
```

### Rubric Score Notes

| Rubric | Score | Notes |
|---|---:|---|
| Research | 94/100 | Strong source limits, proof warnings, and transaction-oriented questions. Loses points because deadline proof is absent and professional review may be needed. |
| Handoff | 97/100 | Correct owner, clear task request, explicit proof state, and strong human review gate. Minor loss because some transaction owners will be assigned in the next folder. |
