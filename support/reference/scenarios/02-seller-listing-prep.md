# Scenario 02: Seller Listing Prep

Seller-side flow that requires intake, market research, and a consult-invite draft. Tests the architecture against the other side of the deal.

## Raw Request

```text
Got a call from the Williams couple. They want to list their place at 1207 Mockingbird Ln in 78745 in early November. Three years there, did a kitchen update in 2024. Considering selling but want a market read first before committing to listing with us.
```

## Routing Decision (00_orchestrator)

Sequence: `01_lead_qualifier` → `02_property_research` → `03_client_communication`.

**Why.** Seller leads need intake first (decision-maker, timeline, occupancy, listing agreement status), then market research (recent comps, neighborhood trends, days-on-market), then a consult invite that frames the next step without overpromising on price.

**Compliance scan:**
- Fair housing: low, seller-side intake, no protected-class signals yet.
- Advertising or broker-review: medium, any price claim is regulator-sensitive.
- Legal, tax, lending, appraisal, or inspection advice: medium, no valuation commitments.
- Privacy or sensitive data: low.
- Source reliability: high, comps and DOM data must come from approved sources.
- Listing agreement: NOT signed — block any "we'll list it for $X" language until a listing agreement is signed.

## Handoff Chain

Scenario packets are abbreviated for readability. In live use, add the shared metadata from `../handoff-contracts.md`, check output against `../agency-standard.md`, and update the lead/deal log for Deal Desk visibility.

### Packet 1: 00 → 01

```md
From: 00_orchestrator
To: 01_lead_qualifier
Matter ID: MOCK-SELLER-002
Stage: Seller intake
Client or lead: The Williams
Matter: Seller exploring November listing, wants market read first
Urgency: Medium, target listing window 6-8 weeks out

## Known Facts
- Property: 1207 Mockingbird Ln, 78745.
- Three years in the home.
- Kitchen update in 2024.
- Target list date: early November.
- Want a market read before committing.

## Missing Information
- Blocking: decision-maker status (both Williams agree?), listing agreement status, occupancy plans.
- Helpful: condition beyond kitchen, mortgage payoff if relevant later, motivation.

## Requested Output
Seller lead summary, listing agreement status, handoff to property research for comps.
```

### Packet 2: 01 → 02

```md
From: 01_lead_qualifier
To: 02_property_research
Matter ID: MOCK-SELLER-002
Stage: Market research
Client or lead: The Williams
Matter: Pull comps and market context for 1207 Mockingbird Ln, 78745
Urgency: Medium
Current status: Warm seller, no listing agreement signed

## Known Facts
- Property: 1207 Mockingbird Ln, 78745.
- 2024 kitchen update.
- Both Williams are decision-makers (intake confirmed).
- Owner-occupied, planning to relocate after sale.

## Missing Information
- Blocking: verified property facts (square footage, bed/bath, lot size from county records).
- Helpful: recent comps within 0.5 mi, current active listings, DOM trends.
- Can wait: detailed condition assessment until in-person consult.

## Compliance Flags
- Source reliability: high, comps and DOM from team-approved MLS only.
- Listing agreement: not signed; output must NOT propose a specific list price.

## Requested Output
Market brief: comp range, current activity, neighborhood velocity, source-confidence per data point. Do NOT recommend a list price.

## Lead Qualifier Output
- Lead Temperature: Warm
- Recommended next action: comp brief + consult invite. Frame as "let's talk through what the data shows" not "we'll list it for $X."
```

### Packet 3: 02 → 03

```md
From: 02_property_research
To: 03_client_communication
Matter ID: MOCK-SELLER-002
Stage: Consult invite draft
Client or lead: The Williams
Matter: Draft consult-invite email with market overview, NO list-price claim
Urgency: Medium
Current status: Research complete, ready for cautious client-facing draft

## Known Facts (from research)
- 6 recent comps within 0.5 mi closed in last 90 days, range 600k-735k.
- Active listings in immediate area show 30-50 DOM average (verified by team-approved MLS, last checked today).
- 2024 kitchen update is a positive but undocumented in MLS comp data.
- Neighborhood velocity: modestly slowing for fall, typical pattern.

## Missing Information
- Blocking: in-person property assessment before any price discussion.
- Helpful: kitchen update receipts, any other improvements documented.

## Compliance Flags
- Advertising or broker-review: medium, draft must not claim a specific list price.
- Source reliability: high, all data has cite-dates.
- Fair housing: low.

## Source And Proof State
- Source of truth: team-approved MLS, checked today.
- Source checked at: today.
- Needs recheck before: consult meeting.
- Proof available: comp list, DOM averages (internal).
- Proof missing: in-person property assessment.

## Requested Output
Email draft inviting the Williams to a 45-minute consult. Mention the comp range as a band, NOT a single price. Reference the 2024 kitchen update as a positive that should be documented. Frame the consult as "let's walk through what the data shows together."

## Human Review
- Reviewer needed: Diana.
- Review reason: any price language to a potential seller is regulator-sensitive.
- Cannot proceed until: Diana approves price-band language and consult time.
```

## Final Output (drafted by 03_client_communication)

**Draft Status:** Needs Diana review.

**Voice Score:** 17/20.

**Draft:**

> Subject: November listing — let's walk through the data together
>
> Hi Mark and Jen,
>
> Thanks for the call. November is a good window to be thinking about — late fall in Austin tends to favor sellers who price thoughtfully and stage well, and there's still meaningful buyer activity before the holidays slow things down.
>
> Quick read from the comp data on Mockingbird and nearby streets:
>
> - 6 recent sales in the last 90 days landed in the 600k-735k range. That's the band to think in, not a specific number for your place.
> - Active listings are taking 30 to 50 days on market on average. Healthy but not frantic.
> - Your 2024 kitchen update is the kind of upgrade that doesn't always show in MLS data but matters at the buyer's first walk-through. If you have receipts or contractor info, that'll help us tell that story.
>
> Before we land on any number, the right next step is a 45-minute consult at your place. I'll walk through:
>
> 1. What I'm seeing in the comps.
> 2. What I'd want to prep before listing (cosmetic, photos, staging).
> 3. The timeline and contract details.
>
> Three windows that work this week: Wednesday morning, Thursday afternoon, Friday morning. Let me know which fits and I'll confirm.
>
> Diana

**Human Review Notes:**
The draft references the comp range as a band, not a price. The 2024 kitchen update is positioned as a positive that needs documentation. No listing agreement promises. Diana should approve the time windows and confirm she's comfortable with the comp range framing.

## What This Demonstrates

- **Seller-side intake captures listing agreement status as a gate** (parallel to buyer rep agreement on buyer side).
- **The architecture does not assume buyer-only flows.**
- **Comp data is presented as a band with cite-dates, not as a specific price.**
- **Source-of-truth fields prevent the system from inflating a price.**
- **Voice score + human review catches advertising / broker-review risk.**
