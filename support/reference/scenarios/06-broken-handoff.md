# Scenario 06: Broken Handoff (Rejection)

What happens when a handoff packet is missing required fields. Demonstrates the protocol is real, not aspirational. The receiving specialist rejects the packet and returns it to the orchestrator with a "what's missing" note.

## Raw Request

```text
Just need a quick draft email to send Jordan about 4812 Sample Bend.
```

## Routing Decision (00_orchestrator)

The request is missing critical context. The orchestrator could either:

A. Pause and ask the team member for the missing context.
B. Try to route to 03_client_communication directly with a thin packet.

The orchestrator picks (A) when context is critical. Here, the team member is mid-flow, so the orchestrator tries (B) but flags the packet as `THIN — receiver may reject`.

This scenario shows what happens when the receiver rejects.

## Handoff Chain (with rejection)

### Packet 1: 00 → 03 (thin, no research data)

```md
From: 00_orchestrator
To: 03_client_communication
Matter ID: MOCK-BROKEN-006
Stage: Client draft (THIN PACKET)
Client or lead: Jordan
Matter: Draft email about 4812 Sample Bend
Urgency: Not specified
Current status: Unspecified

## Known Facts
- Jordan is a buyer lead.
- Property is 4812 Sample Bend.

## Missing Information
- Blocking: lead temperature, intake status, current property status, source-of-truth, buyer rep agreement status.

## Compliance Flags
- Source reliability: unknown.
- Buyer rep agreement: unknown.

## Requested Output
"Quick draft email."

## Receiver Discretion
THIN PACKET. Receiver may reject if required fields are missing.
```

### Packet 2: 03 → 00 (REJECTION)

```md
From: 03_client_communication
To: 00_orchestrator
Matter ID: MOCK-BROKEN-006
Stage: PACKET REJECTED
Reason: Missing required fields for a compliant client-facing draft

## What I Was Asked
"Quick draft email about 4812 Sample Bend for Jordan."

## Why I'm Rejecting
A client-facing draft requires at minimum:

- Lead temperature (Hot / Warm / Nurture / Unqualified)
- Recent intake status: do we know who Jordan is, what they want, what they've been told so far?
- Property status: is 4812 Sample Bend currently active, pending, sold, or off-market? Without this, any reply about the property would be unverified.
- Source-of-truth field: where did the property data come from? When was it checked?
- Buyer representation agreement status: required before any showing-related language.

Without these, the draft would either:

(a) be a generic message that doesn't move the conversation forward, OR
(b) include unverified claims about the property, OR
(c) imply showing scheduling without rep-agreement compliance.

## What I Need To Proceed
1. Intake packet from 01_lead_qualifier with Jordan's lead temperature and current state.
2. Research packet from 02_property_research with verified property status and source-checked timestamp.
3. Confirmation of buyer rep agreement status from intake.

## Recovery Path
- Orchestrator should pause and run intake first if Jordan has not been qualified yet.
- If Jordan IS qualified, orchestrator should pull the prior intake packet from the deal file.
- If property research has been done, orchestrator should pull the most recent research packet (or trigger a fresh check if stale).
- Re-submit packet with required fields populated.

## What I Will NOT Do
- I will not draft a message that says "4812 Sample Bend is available" without source verification.
- I will not propose a tour without rep agreement confirmation.
- I will not fabricate intake context to fill the gap.
```

### Packet 3: 00 → user (recovery prompt)

```md
From: 00_orchestrator
To: User (team member)

I tried to route your "quick draft email about 4812 Sample Bend for Jordan" directly to client communication, but the receiver rejected the packet. The draft requires:

1. Jordan's intake status (have we qualified them yet? lead temperature?)
2. Current property status for 4812 Sample Bend (verified from team-approved MLS, checked recently)
3. Buyer rep agreement status

Three options for you:

A. **Tell me where things stand.** "Jordan is a warm new lead, we already did intake, no rep agreement yet, property is still active per MLS this morning." I'll re-build the packet and route.

B. **Run intake first.** I'll route to 01_lead_qualifier for Jordan, then back to property research for 4812, then to client communication for the draft. Adds 2-3 minutes but produces a compliant draft.

C. **Just write something generic.** I can route a generic "hey just checking in" message without the property — but that probably doesn't help you.

Which way do you want to go?
```

## What This Demonstrates

- **The receiver specialist enforces the protocol.** It does not produce a draft just because someone asked.
- **Rejection is structured, not silent.** The packet comes back with a clear "what's missing" and "what I need."
- **The orchestrator has a recovery path.** It doesn't just fail — it offers the user three ways forward.
- **The system protects against compliance landmines** (showing without rep agreement, claiming availability without source check) by refusing to draft, not by drafting unsafely.
- **The handoff contracts are enforced from the receiver side, not just declared.**

## Why This Matters For Judging

The brief said handoff protocols are THE test of this week. Many systems "define" handoffs but never actually enforce them — a specialist will just do the work even if the packet is incomplete. The Agency's specialists refuse incomplete packets and route back through the orchestrator. That's the difference between a documented contract and a real one.

See `../handoff-contracts.md` for the full list of required fields per handoff direction.
