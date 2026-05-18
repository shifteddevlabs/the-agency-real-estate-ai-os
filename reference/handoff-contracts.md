# Handoff Contracts

The brief said the handoff protocol is the test of this week. This document formalizes it. Every handoff direction has required fields, forbidden fields, and explicit rejection conditions.

A receiver specialist that gets a packet missing required fields returns it to the orchestrator with a rejection note. This is demonstrated in [`scenarios/06-broken-handoff.md`](scenarios/06-broken-handoff.md).

## Universal Required Fields

Every packet in The Agency must include:

| Field | Why |
|---|---|
| `From` | Receiver needs to know which specialist sent it (for routing back if rejected). |
| `To` | Explicit destination prevents ambiguous handoffs. |
| `Matter ID` | Threads the work across specialists. A deal without a Matter ID can't be traced or audited. |
| `Stage` | Tells the receiver what state of work this is (intake, research, draft, decision, closing-week). |
| `Client or lead` | Names the human. Anonymous packets get rejected. |
| `Matter` | One-line description of what's being asked. |
| `Urgency` | High / Medium / Low. Drives queue order and deadline awareness. |
| `Current status` | What's been done so far, in one sentence. |

A packet missing ANY of the eight is rejected at the receiver.

## Universal Required Sections

In addition to the header fields, every packet must include four sections (some can be empty, but the headers must exist):

- `## Known Facts` — what's verified.
- `## Missing Information` — broken into Blocking / Helpful / Can wait.
- `## Compliance Flags` — at minimum: fair-housing, advertising/broker-review, advice-risk, privacy, source-reliability, wire-fraud, buyer-rep-agreement, language.
- `## Requested Output` — what the receiver should produce.

## Universal Forbidden Content

Across all handoffs, packets must NEVER contain:

- Wire instructions, account numbers, or routing numbers.
- Client SSN, bank account, mortgage payoff (unless explicitly needed for a specific stage, redacted if so).
- Protected-class assumptions or steering language.
- Unverified facts presented as verified.
- Any content the orchestrator's compliance scan flagged as high-risk without the corresponding mitigation step noted in the packet.

## Per-Direction Contracts

### 00 → 01 (orchestrator → lead qualifier)

**Required additions:**
- Lead type signal: buyer / seller / renter / investor / referral / open-house / portal-inquiry / returning.
- Preferred language signal if known.
- For buyer signals: prior buyer rep agreement context if any (current agent? lapsed? unclear?).
- For returning client signals: prior relationship summary (from CRM or prior packets).

**Forbidden:**
- Pre-judging lead temperature (that's 01's job).

**Receiver rejects if:**
- Lead type is "unknown" and no clarifying signals are passed.

### 01 → 02 (lead qualifier → property research)

**Required additions:**
- Client criteria (price band, areas, must-haves, deal breakers).
- Specific research question(s), not just "tell me about the property."
- Lead temperature.
- Fair-housing-sensitive details that 02 must AVOID (e.g., reason for move if protected-class).

**Forbidden:**
- Showing scheduling language (02 doesn't schedule).
- Client name in pre-research notes if research is being shared with external parties.

**Receiver rejects if:**
- Specific research question missing — 02 won't do generic "research the address" without scope.
- Criteria are too vague to score property fit (e.g., "wants a nice house").

### 01 → 03 (lead qualifier → client communication)

**Required additions:**
- Lead temperature.
- Channel (email / text / call script / DM).
- Tone needed.
- Questions to ask in the reply (if any).
- Call-to-action.
- Buyer rep agreement status (REQUIRED for buyer leads; the draft cannot propose a showing without it).

**Forbidden:**
- A "send this" instruction (03 always drafts; humans send).
- Pre-written voice that overrides Diana's profile.

**Receiver rejects if:**
- Channel is missing.
- Buyer-side packet with no rep-agreement status.

### 01 → 04 (lead qualifier → transaction coordinator)

**Required additions:**
- Confirmation the lead is past intake and in a live transaction.
- Signed buyer rep agreement OR signed listing agreement on file.
- Executed contract OR appointment status.
- Already-verified dates from a human.

**Forbidden:**
- Unverified deadlines passed as final.
- Speculative "I think the option ends Friday."

**Receiver rejects if:**
- Representation agreement status is unconfirmed.
- No executed contract or appointment.

### 02 → 03 (property research → client communication)

**Required additions:**
- Source of truth for every fact (which MLS, county record, etc.).
- Source-checked-at timestamp.
- Source confidence label per fact (high / medium / low).
- What needs verification before client reply.

**Forbidden:**
- Listing-language ("must see," "rare gem," "won't last").
- Specific price claims unsupported by comps.
- Neighborhood characterizations beyond client-stated criteria.

**Receiver rejects if:**
- Source-checked-at timestamp missing.
- Any fact is labeled "high confidence" without a source.

### 02 → 04 (property research → transaction coordinator)

**Required additions:**
- Verified property facts that affect contract terms (square footage, lot size, HOA, age, deed restrictions, etc.).
- Source documentation references.

**Forbidden:**
- Speculative property history.
- Pricing or valuation claims.

**Receiver rejects if:**
- Required contract-relevant facts missing.

### 03 → 04 (client communication → transaction coordinator)

**Required additions:**
- Confirmed delivery of a client-facing message (Diana sent it, with timestamp).
- Client response or commitment that triggered transaction-stage work.

**Forbidden:**
- Pre-confirmation transaction work ("client says they want to make an offer" is not the same as "offer signed").

**Receiver rejects if:**
- The trigger event isn't confirmed (verbal commitments aren't enough).

### 04 → 03 (transaction coordinator → client communication)

**Required additions:**
- Transaction stage (option period day X of Y, financing contingency window, closing T-N).
- Verified dates from the executed contract.
- Compliance flags specific to the stage (wire-fraud warning required for closing-week messages).
- Decision required from the client, if any, with deadline.

**Forbidden:**
- Wire instructions or account details.
- Estimated severity or repair cost claims (those come from licensed specialists, not 04).
- Drafts that propose contract amendments without Diana's approval gate.

**Receiver rejects if:**
- Stage is unclear.
- Verified dates are missing.

### Any → 00 (escalation back to orchestrator)

**Required additions:**
- Reason for escalation (compliance risk, scope mismatch, missing data, multi-owner work).
- What the original packet asked for.
- What's blocking.

**Forbidden:**
- Vague "this is too hard" returns. Must name the specific block.

**Receiver behavior:**
- Orchestrator re-routes, asks the user for missing context, or escalates to broker/Diana.

### 00 → Escalation (broker, attorney, lender, title, specialist)

**Required additions:**
- Specific escalation owner.
- Reason in one sentence.
- Time-sensitivity.
- What the system has NOT done that the escalation owner needs to do.

**Forbidden:**
- Generic "Diana, please help" without specifics.

**Receiver behavior:**
- Human owner takes the next step. System pauses on this Matter ID until human signals resolution.

## Minimum Packet vs Full Packet

The full schema in [`../README.md`](../README.md) (Handoff Packet section) lists ~15 fields. Use the full schema for:

- Compliance-sensitive handoffs (any wire-fraud, fair-housing, advertising, or representation issue).
- Stage transitions (intake → research → draft, or research → transaction).
- Any handoff that crosses an externally-visible boundary (something a client, broker, attorney, or lender will see).

Use a minimum packet (the 8 universal required fields plus the 4 required section headers) for:

- Quick internal routing inside the orchestrator.
- Routine continuation of an established Matter ID where context is already known.

When in doubt, use the full packet. The extra fields cost nothing if not used; the missing fields can cost a deal.

## Audit Trail

Because every packet has a Matter ID and Stage, a deal's history can be reconstructed by chaining packets in order. This is intentional. A future v2 could persist packets as JSON files for audit/replay, but v1 keeps them in-chat for the human-paste model documented in [`design-notes.md`](design-notes.md).

## Related

- [`scenarios/06-broken-handoff.md`](scenarios/06-broken-handoff.md) — worked example of a rejection.
- [`failure-modes.md`](failure-modes.md) — catalog of what goes wrong and how the system recovers.
- Each specialist's `handoff.md` — what THAT specialist receives and produces.
