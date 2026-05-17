# Option Period Playbook

What to track and what to draft during the buyer's option period in a Texas residential resale transaction.

## What The Option Period Is

A buyer's paid right to terminate the contract for any reason and recover earnest money. The buyer pays a non-refundable option fee (typically $100 to $500 in Austin) for this right. The seller gets to keep the option fee regardless of what the buyer decides.

## Day Zero

The clock starts the day AFTER the contract is fully executed (signed by all parties, with notice received). Day 1 is the next calendar day.

Verify the effective date against the executed contract. If the effective date is unclear, mark the option deadline as `unverified` and escalate to broker or title.

## Typical Length

- 5 to 7 calendar days is common in Austin.
- Longer (10+ days) is unusual and worth flagging if it appears.
- Shorter (3 days) is aggressive and signals a seller's market or a competitive offer.

## What Must Happen Inside The Option Period

| Task | Owner | Deadline |
|---|---|---|
| Confirm receipt of executed contract (all signed pages) | Team | Day 1 |
| Confirm earnest money delivered to title | Team verifies with title | Within 3 days of effective date |
| Confirm option fee delivered to seller | Team or title | Within 3 days of effective date |
| Schedule inspection | Buyer's team | Day 1 to 2 |
| Inspection performed | Inspector | Day 2 to 4 |
| Inspection report received | Buyer | Day 3 to 5 |
| Buyer's specialist consultations (HVAC, foundation, roof) if needed | Buyer | Before option ends |
| Decision: accept as-is, request repairs, request credit, or terminate | Buyer + Diana | Before option ends |
| Amendment (TREC 39) drafted and submitted | Buyer's agent | Before 5 PM on last day if requesting repairs/credit |
| Termination notice (TREC 38) delivered if terminating | Buyer's agent | Before 5 PM on last day |

## The "By 5 PM" Rule

Termination notice and amendments must be delivered AND received by 5 PM local time on the last day of the option period. Email timestamps matter. Out-of-office replies do not stop the clock.

If the last day is a Saturday, Sunday, or federal holiday, the deadline rolls to 5 PM on the next business day.

## When To Escalate To Broker

- Buyer wants to terminate after the option period ends. (Cannot recover earnest money in most cases.)
- Seller refuses to negotiate any repairs and buyer is on the fence.
- Inspector finds a material defect not previously disclosed.
- Buyer wants to modify the contract beyond a standard amendment.
- A wire fraud attempt occurs.

## Client Update Draft Points (mid-option)

For client status updates during the option period, hand off to `03_client_communication/` with these talking points:

- Where we are in the option period (day X of Y).
- What's been done (inspection scheduled, inspection completed, report reviewed).
- What's left to decide.
- What we recommend based on the report.
- The deadline by which the decision must be made.
- A clear "what happens if we do nothing" framing.

Never tell a client the option period is final or extended without verification against the executed contract.

## Common Failure Modes

- **Trusting the listing agent's "we have until Friday" email.** Verify against the contract.
- **Submitting the amendment at 4:55 PM.** Give yourself a 1-business-day buffer.
- **Missing the option fee delivery deadline.** Earnest money and option fee are two separate items with two separate deadlines.
- **Confusing option period with financing contingency.** Option is short and broad (any reason). Financing contingency is longer and specific (financing fails).
- **Assuming the option period extends automatically.** It doesn't. Extensions require a written amendment signed by both parties.

## Output Format

When the orchestrator routes an option-period question here, produce:

```md
## Option Period Status
- Effective date:
- Last day of option:
- Days remaining:
- Inspection: scheduled / completed / report received
- Decision needed by:

## Outstanding Tasks
[table]

## Decision Required
[what the buyer needs to decide, by when]

## Recommended Action
[one sentence]

## Escalations
[any items requiring broker, attorney, lender, inspector]

## Client Update Draft Points
[bullets for handoff to 03_client_communication]
```
