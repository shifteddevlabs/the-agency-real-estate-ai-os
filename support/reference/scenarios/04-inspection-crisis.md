# Scenario 04: Inspection Crisis Mid-Option

A deal hits trouble during the option period. Tests the transaction coordinator's renegotiation playbook and the time-sensitive decision support flow.

## Raw Request

```text
Inspection came back on the Lytle deal. Foundation cracks the inspector wants a structural engineer to look at, HVAC near end of useful life, and a drainage issue on the east side of the lot. Buyer Sarah is rattled, called Diana sounding shaky. Option ends Friday at 5 PM. We need to figure out what to ask the seller for and draft Sarah a calming-but-honest update.
```

## Routing Decision (00_orchestrator)

Sequence: `04_transaction_coordinator` (with inspection-renegotiation-playbook) → `03_client_communication`.

**Why.** The deal is past intake and past research. It's mid-option. The transaction coordinator owns the renegotiation structure; communication owns the draft to the client. Order matters: structure first, draft second, both reviewed by Diana before the client sees anything.

**Compliance scan:**
- Source reliability: HIGH. Inspector's findings are the source of truth on severity; do not paraphrase.
- Legal, tax, lending, appraisal, or inspection advice: HIGH. The system does not estimate repair costs, judge severity beyond inspector's wording, or recommend a path. It structures the options for Diana and the client.
- Time-sensitive: option ends Friday 5 PM. All actions must complete before then.
- Buyer rep agreement: confirmed on file.

## Handoff Chain

### Packet 1: 00 → 04

```md
From: 00_orchestrator
To: 04_transaction_coordinator (inspection-renegotiation-playbook)
Matter ID: MOCK-DEAL-004
Stage: Inspection renegotiation
Client or lead: Sarah Lytle
Matter: Three inspection findings, decision required before Friday 5 PM
Urgency: HIGH, option ends Friday 5 PM, ~72 hours

## Known Facts
- Inspection received today.
- Findings (inspector's wording):
  1. Foundation cracks; inspector recommends structural engineer evaluation.
  2. HVAC near end of useful life.
  3. Drainage issue on east side of lot.
- Buyer Sarah is anxious.
- Option period ends Friday 5 PM.
- Buyer rep agreement on file.

## Missing Information
- Blocking: structural engineer's evaluation (severity), HVAC contractor's evaluation (remaining life + replacement cost range), drainage specialist if needed.
- Helpful: Sarah's risk tolerance, financial flexibility for cash-to-close adjustments.

## Compliance Flags
- Source reliability: HIGH, use inspector's exact language.
- Professional advice: HIGH, do not estimate severity, cost, or remaining life — those come from licensed specialists.
- Legal advice: do not advise Sarah to terminate or proceed without Diana's review.

## Requested Output
Structured framing of Sarah's four options (accept as-is, request repairs, request credit, terminate). For each: implications, timeline, what's needed, what to ask the seller. Draft amendment language if proceeding with repair-or-credit. Client update draft points to hand to 03.
```

### Packet 2: 04 → 03

```md
From: 04_transaction_coordinator
To: 03_client_communication
Matter ID: MOCK-DEAL-004
Stage: Client update draft
Client or lead: Sarah Lytle
Matter: Draft a calming-but-honest update for Sarah about inspection findings and decision path
Urgency: HIGH, send today

## Known Facts (from 04 output)
- Three findings, all flagged for specialist evaluation before any severity claim.
- Option ends Friday 5 PM.
- Sarah has four paths: accept as-is, request repairs, request credit, terminate.
- Recommended structure: get structural engineer + HVAC contractor opinions Wednesday, decide Thursday, deliver amendment or termination Friday by noon.

## Missing Information
- Blocking: Sarah's gut read after the specialist evaluations come in.
- Helpful: Sarah's confidence in the rest of the deal.

## Compliance Flags
- Source reliability: HIGH, draft must use inspector's wording, not coordinator's paraphrase.
- Professional advice: HIGH, draft must NOT claim severity or cost ranges.
- Voice: Diana's voice. Sarah is anxious. Lead with calm. Acknowledge the report's weight. Frame the next steps clearly.

## Source And Proof State
- Source of truth: inspection report (attached, in deal file).
- Source checked at: today.
- Needs recheck before: any specialist statement reaches Sarah.
- Proof available: inspection report.
- Proof missing: structural engineer, HVAC, drainage evaluations.

## Requested Output
Email draft to Sarah. Calming tone, honest about the report's seriousness, structures her four paths without recommending one, names the specialist evaluations as the next gate, names the Friday deadline plainly, ends with a phone-call invite for tomorrow.

## Human Review
- Reviewer needed: Diana.
- Review reason: anxious client + time-sensitive decision + protected from over-promise.
- Cannot proceed until: Diana reviews and approves.
```

## Final Output (drafted by 03_client_communication)

**Draft Status:** Needs Diana review.

**Voice Score:** 18/20.

**Draft:**

> Subject: Inspection report — let's walk through it together
>
> Hi Sarah,
>
> Inspection report just came in. Three items the inspector flagged for us to look at more closely:
>
> 1. Foundation cracks. The inspector recommends a structural engineer take a look before we make any judgments on severity.
> 2. HVAC near end of useful life. Worth a quick read from an HVAC contractor on remaining years and replacement cost range.
> 3. Drainage issue on the east side of the lot. May or may not need a specialist — we'll know after the structural engineer.
>
> Here's the practical read. You have four paths from here:
>
> 1. **Accept the house as-is** and move forward. Worth considering if the specialists come back saying these are normal-for-the-age issues.
> 2. **Ask the seller to repair** the items they're willing to fix.
> 3. **Ask the seller for a credit at closing** so you can handle the work yourself after the deal. Often cleaner because you control the quality of the work.
> 4. **Terminate within the option period.** You'd recover your earnest money. You'd lose the option fee. This is your right; it's not a failure.
>
> Two things I want to make sure you hear:
>
> - None of this is a recommendation yet. I want the specialists to weigh in first.
> - The option ends Friday at 5 PM, so we have to decide by Friday morning at the latest.
>
> Here's what I'd like to do: I'll set up the structural engineer for Wednesday morning and an HVAC read by Wednesday afternoon. Thursday morning you and I get on the phone, look at what the specialists said, and decide. Friday morning we deliver whatever we're going to deliver.
>
> Want to grab 15 minutes tomorrow night to talk through any of this? I know the report can feel heavy on first read. It's not.
>
> Diana

**Human Review Notes:**
The draft uses the inspector's wording verbatim. It does not claim severity, cost, or remaining life. All four buyer paths are laid out without recommendation. The Friday deadline is named. A phone call is offered tomorrow. Diana should confirm the specialist timing (structural Wed, HVAC Wed, decision Thu) is realistic before sending.

## What This Demonstrates

- **The renegotiation playbook produces structure, not recommendations.**
- **The system refuses to estimate severity or cost — those come from licensed specialists.**
- **Time-sensitive deadlines (option ends Friday 5 PM) are surfaced plainly.**
- **The client's emotional state (anxious) shapes tone without changing facts.**
- **The handoff from 04 to 03 separates structure (4) from voice (3).**
- **Multiple specialists are sequenced in days, not all-at-once.**
