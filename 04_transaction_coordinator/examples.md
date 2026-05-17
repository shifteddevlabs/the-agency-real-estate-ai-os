# Examples

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
| Task | Owner | Due date | Source | Status | Proof needed | Next action |
|---|---|---|---|---|---|---|
| Verify executed contract dates | Diana | Today | Executed contract | Open | Contract date fields checked | Confirm option deadline |
| Confirm inspection appointment | Team | Today | Inspector confirmation | Open | Calendar invite or email | Verify time and access |
| Prepare inspection-review plan | Diana | After report | Inspection report | Open | Report received | Review with client |

## Escalations
- Same-day deadline risk if option date is close.
- Legal or contract interpretation goes to broker or attorney.
```

## Example 2, Missing Document

Input:

```text
We still need seller disclosure and HOA docs.
```

Output:

```md
## Blockers
- Seller disclosure missing.
- HOA docs missing.

## Checklist
| Task | Owner | Due date | Source | Status | Proof needed | Next action |
|---|---|---|---|---|---|---|
| Request seller disclosure | Diana/team | Unverified | Contract/listing file | Open | Document received | Ask listing side |
| Request HOA docs | Diana/team | Unverified | Contract/listing file | Open | HOA packet received | Ask listing side or title |

## Client Update Draft Points
- We are tracking both items.
- We will review once received.
- Do not imply document contents before they arrive.
```

## Example 3, Inspection Concern

Input:

```text
Inspection found HVAC age, roof concern, and drainage issue.
```

Output:

```md
## Transaction Status
Inspection findings need strategy review.

## Escalations
- HVAC: licensed HVAC contractor if cost or remaining life matters.
- Roof: roofer evaluation if buyer wants repair or credit discussion.
- Drainage: specialist or inspector clarification.
- Strategy: Diana and client decide what to request.

## Client Update Draft Points
- Inspection report raised three items worth discussing.
- Next step is to review severity, cost exposure, and negotiation options.
- Avoid giving repair-cost estimates without quotes.
```

