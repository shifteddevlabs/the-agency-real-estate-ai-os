# Closing Week Checklist

The 5-day-out sequence for a Texas residential closing. Use this when a deal hits "T-5 business days" until close.

> ## ⚠ WIRE FRAUD WARNING (read first)
>
> Real estate is the #1 industry for business-email-compromise fraud. The most common attack:
>
> 1. Scammers monitor the buyer's email during the deal.
> 2. At the last minute, they impersonate the title company and email "updated wiring instructions."
> 3. The buyer wires their down payment (often $100K+) to the scammer.
> 4. Money is gone. Wire transfers are typically not recoverable.
>
> **Rules this system enforces:**
>
> - Do NOT include wire instructions, account numbers, or routing numbers in any draft, checklist, or message.
> - Do NOT relay wire instructions from one party to another. Even if the client asks.
> - Direct the buyer to call the title officer using a number from a verified prior email (not from the new email with "updated" instructions).
> - Title companies will NEVER email updated wire instructions. Any such email is a scam until phone-verified.
> - Any request that mentions wire instructions, account changes, or "updated" payment info gets flagged and escalated to Diana and title immediately.

## T-5 Business Days

| Task | Owner | Status check |
|---|---|---|
| Confirm closing date and time with title | Team | Email confirmation from title |
| Confirm closing location (in-person, mobile notary, remote online notarization) | Team | Written confirmation |
| Confirm financing is cleared to close (CTC) | Lender → Diana | "Clear to close" email or call |
| Final repairs verified (if applicable) | Buyer's team | Receipts and warranties received |
| Order final utilities transfer (date matches closing or possession) | Buyer | Utility company confirmations |
| Confirm earnest money still on deposit | Title | Title statement |

## T-3 Business Days

| Task | Owner | Status check |
|---|---|---|
| Receive Closing Disclosure (CD) from lender | Buyer's lender | CD signed and returned |
| Buyer reviews CD against estimate | Buyer + Diana | Note any discrepancies |
| Wire instructions verified by phone with title | Buyer + Diana | NEVER trust emailed wire instructions without phone verification |
| HOA estoppel received and reviewed | Title | Document in closing file |
| Survey or T-47 affidavit confirmed | Title | Document in closing file |

The 3-business-day CD rule is federal (TILA-RESPA). Closing cannot happen until the buyer has had the CD for 3 business days. If anything material changes on the CD, the 3-day clock restarts.

## T-1 Business Day

| Task | Owner | Status check |
|---|---|---|
| Final walk-through | Buyer + Diana | Property in agreed condition |
| Photos of any new damage or issues | Buyer | Time-stamped photos |
| Confirm closing time, parking, ID requirements | Title | Email or call |
| Confirm closing funds wired (or wire scheduled) | Buyer | Title confirms receipt |
| Confirm photo ID matches contract name (no nicknames) | Buyer | ID copy ready |

## Closing Day

| Task | Owner | Status check |
|---|---|---|
| Buyer arrives 15 minutes early | Buyer | — |
| Settlement statement reviewed line by line | Diana + buyer | Initials on each page |
| Documents signed and notarized | Buyer + title | All signatures captured |
| Funding confirmed | Title | Lender funds receipt |
| Keys, garage remotes, gate codes transferred | Seller/title | Buyer receives physical items |
| Possession transferred per contract | Per contract | Verify timing |
| Recording confirmed | Title | County recording number provided |

## What To Watch For

- **Wire fraud.** The most common scam in real estate. Title companies will NEVER email wiring instructions and then call to update them. Always verify the wire instructions by calling the title officer directly using a number you already know (not one from an email).
- **CD discrepancies.** If anything material on the CD differs from prior estimates, the 3-day clock restarts and closing delays. Common triggers: changed interest rate, new fees, changed escrow.
- **Insurance binder not received.** Required for closing on financed deals. Confirm with the lender by T-3.
- **Power-of-attorney requirements.** If buyer or seller can't attend closing, a POA must be signed in advance, notarized, and approved by title and lender. Set this up at T-7 business days minimum.
- **Possession timing.** If seller is staying in the home after closing (leaseback), confirm the leaseback addendum is signed and the daily rent is correct.
- **Final walk-through surprises.** If repairs aren't done or new damage exists, do NOT close. Delay and resolve. Closing waives most claims about visible condition.

## Mandatory Escalations Closing Week

Pull in the appropriate party immediately if:

- Wire instructions arrive by email without prior phone confirmation. Title officer by phone, no exceptions.
- CD differs materially from prior estimates. Lender and Diana.
- Final walk-through reveals new issues. Diana, broker if material.
- Seller refuses to provide possession on the contracted date. Diana, attorney if dispute persists.
- Funding is delayed past closing time. Lender, title.
- Property damage occurs between contract and closing. Broker, insurance, possibly attorney.

## Output Format

When the orchestrator routes a closing-week question here, produce:

```md
## Closing Status
- Closing date and time:
- Days out:
- Location:
- Cleared to close: yes / no / pending
- CD received and 3-day clock satisfied: yes / no / restarted

## Checklist Status
[mark each T-5, T-3, T-1, closing day task as done / pending / blocked]

## Blockers
[any items preventing closing]

## Wire Fraud Check
[has wire info been verified by phone? when?]

## Final Walk-Through
- Scheduled:
- Completed:
- Issues found:

## Escalations
[any items requiring broker, lender, title, attorney]

## Client Update Draft Points
[bullets for handoff to 03_client_communication]
```

## What This Does Not Cover

- New-construction closings (builder schedules, certificate of occupancy, builder warranty paperwork).
- Investor or assignment-of-contract closings.
- Foreclosure, short sale, or REO closings (lender-specific timelines override standard).
- Out-of-state buyer signings (mail-away).

Escalate any of the above to broker for transaction-specific guidance.
