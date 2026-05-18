# Examples

These examples show transaction coordination output plus the handoff to client communication. The coordinator tracks, flags, and structures work. Diana decides strategy.

## Example 1, Accepted Offer

Input:

```text
Offer accepted. Option period ends Friday at 5 PM. Inspection tomorrow. Need checklist.
```

Output:

```md
## Transaction Status
Accepted offer, early option-period stage.

## Key Dates
- Inspection: tomorrow, source unverified.
- Option period deadline: Friday 5 PM, source unverified until checked against executed contract.

## Checklist
| Task | Owner | Due date | Source of due date | Status | Blocker | Proof needed | Next action |
|---|---|---|---|---|---|---|---|
| Verify executed contract dates | Diana | Today | Executed contract | Open | Contract not attached | Contract date fields checked | Confirm effective date and option deadline |
| Confirm inspection appointment | Team | Today | Inspector confirmation | Open | Time and access unverified | Calendar invite or email | Verify time and access |
| Prepare inspection-review plan | Diana | After report | Inspection report | Open | Report not received | Report received | Review with client |

## Blockers
- Executed contract is not attached.
- Option deadline is unverified.

## Escalations
- Same-day deadline risk if option date is close.
- Legal or contract interpretation goes to broker or attorney.

## Client Update Draft Points
- Inspection is planned, but exact timing should be verified.
- Option deadline must be verified against the executed contract.
- Client should not rely on Friday at 5 PM until Diana confirms.

## Handoff Packet
From: `04_transaction_coordinator`
To: `03_client_communication`
Matter ID: `MOCK-TX-OPTION-001`
Stage: Option-period client update
Client or lead: Buyer client
Matter: Accepted offer, inspection, and option deadline
Urgency: High
Current status: Checklist created, dates unverified

## Known Facts
- Offer accepted.
- User says inspection is tomorrow.
- User says option period ends Friday at 5 PM.

## Missing Information
- Blocking:
  - Executed contract.
  - Effective date.
  - Inspection confirmation.
- Helpful:
  - Earnest money and option fee delivery status.
- Can wait:
  - Closing-week logistics.

## Compliance Flags
- Fair housing: not applicable.
- Advertising or broker-review: not applicable.
- Legal, tax, lending, appraisal, or inspection advice: high, do not interpret contract rights.
- Privacy or sensitive data: medium.
- Source reliability: high, deadline unverified.
- Wire fraud: not applicable.
- Buyer rep agreement: confirm in deal file.
- Language: unknown.

## Source And Proof State
- Source of truth: executed contract, not provided.
- Source checked at: not checked.
- Needs recheck before: sending client update or adding deadline to deal file.
- Proof available: user note.
- Proof missing: executed contract and inspection confirmation.

## Requested Output
Draft a careful client update that labels the deadline as pending verification.

## Next Owner
`03_client_communication`

## Human Review
- Reviewer needed: Diana or assigned agent.
- Review reason: unverified contract dates.
- Cannot proceed until: draft caveats the date or Diana verifies it.

## Human Review Needed Before
- sending to a client
- changing a deadline
- adding to a live transaction file
```

## Example 2, Missing Seller Disclosure And HOA Docs

Input:

```text
We still need seller disclosure and HOA docs.
```

Output:

```md
## Transaction Status
Document collection is blocked on seller-side and HOA materials.

## Key Dates
- Seller disclosure deadline: unverified.
- HOA delivery deadline: unverified.

## Checklist
| Task | Owner | Due date | Source of due date | Status | Blocker | Proof needed | Next action |
|---|---|---|---|---|---|---|---|
| Request seller disclosure | Diana/team | Unverified | Contract/listing file | Open | Document missing | Document received | Ask listing side |
| Request HOA docs | Diana/team or title | Unverified | Contract/title file | Open | HOA packet missing | HOA packet received | Ask listing side or title |

## Blockers
- Seller disclosure missing.
- HOA docs missing.
- Contract deadlines not provided.

## Escalations
- Title if HOA documents are title-managed.
- Broker if seller-side delay affects contract rights.

## Client Update Draft Points
- We are tracking both items.
- We will review once received.
- Do not imply document contents before they arrive.

## Handoff Packet
From: `04_transaction_coordinator`
To: `03_client_communication`
Matter ID: `MOCK-DOCS-001`
Stage: Document-status client update
Client or lead: Buyer client
Matter: Missing seller disclosure and HOA docs
Urgency: Medium
Current status: Documents missing, deadlines unverified

## Known Facts
- Seller disclosure is missing.
- HOA docs are missing.

## Missing Information
- Blocking:
  - Contract deadline for seller disclosure.
  - HOA document owner and deadline.
- Helpful:
  - Whether title has ordered the HOA packet.
- Can wait:
  - Client-facing summary of document contents.

## Compliance Flags
- Fair housing: not applicable.
- Advertising or broker-review: not applicable.
- Legal, tax, lending, appraisal, or inspection advice: medium, do not advise rights from missing docs.
- Privacy or sensitive data: medium.
- Source reliability: high, deadlines unverified.
- Wire fraud: not applicable.
- Buyer rep agreement: confirm in deal file.
- Language: unknown.

## Source And Proof State
- Source of truth: executed contract, title file, listing side.
- Source checked at: current chat only.
- Needs recheck before: client update if deadlines are named.
- Proof available: user note.
- Proof missing: contract deadlines and title status.

## Requested Output
Draft a short client update that says the team is tracking the missing documents without implying contents or deadlines.

## Next Owner
`03_client_communication`

## Human Review
- Reviewer needed: Diana or assigned agent.
- Review reason: missing transaction documents.
- Cannot proceed until: no unverified deadline is stated as final.

## Human Review Needed Before
- sending to a client
- adding to a live transaction file
```

## Example 3, Inspection Concern

Input:

```text
Inspection found HVAC age, roof concern, and drainage issue.
```

Output:

```md
## Transaction Status
Inspection findings need structured review during the option period.

## Key Dates
- Option deadline: not provided.
- Inspection report received: yes, per user note.

## Checklist
| Task | Owner | Due date | Source of due date | Status | Blocker | Proof needed | Next action |
|---|---|---|---|---|---|---|---|
| Review inspection report | Diana | Before option deadline | Executed contract | Open | Option deadline missing | Report and deadline verified | Identify items to discuss |
| Get HVAC opinion if needed | Team | Before option deadline | Diana decision | Open | No contractor quote | Contractor response | Ask Diana whether to request quote |
| Get roof opinion if needed | Team | Before option deadline | Diana decision | Open | No roofer quote | Roofer response | Ask Diana whether to request quote |
| Clarify drainage issue | Diana/team | Before option deadline | Inspection report | Open | Severity unknown | Inspector or specialist clarification | Decide if follow-up is needed |

## Blockers
- Option deadline missing.
- Specialist opinions not yet collected.

## Escalations
- HVAC: licensed HVAC contractor if cost or remaining life matters.
- Roof: roofer evaluation if buyer wants repair or credit discussion.
- Drainage: inspector clarification or drainage specialist.
- Strategy: Diana and client decide what to request.

## Client Update Draft Points
- Inspection report raised three items worth discussing.
- Do not estimate repair cost or severity without specialists.
- Next step is to separate what needs a quote, what may be negotiable, and what is ordinary maintenance.

## Handoff Packet
From: `04_transaction_coordinator`
To: `03_client_communication`
Matter ID: `MOCK-INSPECTION-001`
Stage: Inspection client update
Client or lead: Buyer client
Matter: HVAC, roof, and drainage inspection findings
Urgency: High if option deadline is soon
Current status: Inspection concerns identified, strategy not decided

## Known Facts
- Inspection found HVAC age.
- Inspection found roof concern.
- Inspection found drainage issue.

## Missing Information
- Blocking:
  - Option deadline.
  - Exact inspector wording.
  - Whether specialist opinions are needed.
- Helpful:
  - Client's concern level.
  - Quote availability.
- Can wait:
  - Final amendment language.

## Compliance Flags
- Fair housing: not applicable.
- Advertising or broker-review: not applicable.
- Legal, tax, lending, appraisal, or inspection advice: high, do not characterize severity or legal rights.
- Privacy or sensitive data: medium.
- Source reliability: high, exact report wording missing.
- Wire fraud: not applicable.
- Buyer rep agreement: confirm in deal file.
- Language: unknown.

## Source And Proof State
- Source of truth: inspection report and executed contract.
- Source checked at: current chat only.
- Needs recheck before: client update or amendment drafting.
- Proof available: user summary.
- Proof missing: report text, deadline, specialist opinions.

## Requested Output
Draft a calm client update that names the three items, avoids severity claims, and sets up the review call.

## Next Owner
`03_client_communication`

## Human Review
- Reviewer needed: Diana.
- Review reason: inspection strategy and option-period risk.
- Cannot proceed until: draft avoids repair-cost, severity, and negotiation advice.

## Human Review Needed Before
- sending to a client
- changing a deadline
- drafting an amendment
```
