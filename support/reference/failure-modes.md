# Failure Modes

The Lyceum description mentions "what to do when the system breaks." This document catalogs the failure modes The Agency was designed for, per specialist, with the recovery path baked into the architecture.

A system that doesn't acknowledge how it fails is not a real system. These are real.

## 00_orchestrator Failure Modes

### Wrong specialist picked

**What happens:** Orchestrator routes a property research question to `01_lead_qualifier`, or routes an accepted-offer to `02_property_research` instead of `04_transaction_coordinator`.

**How it surfaces:** The receiving specialist's output doesn't fit. The team member notices the response is off.

**Recovery:**
1. Team member says: "Wrong folder. Route to `04_transaction_coordinator` instead."
2. Orchestrator re-routes and creates a fresh packet.
3. No re-typing of the original request.

**Architectural protection:** The orchestrator names the destination in every routing output. Visible mistakes are easier to catch than silent ones.

### Compliance flag missed

**What happens:** Orchestrator routes a request that contains a wire fraud attempt, fair-housing question, or unverified date, without flagging the risk.

**How it surfaces:** Downstream specialist either does unsafe work OR catches the risk and escalates back.

**Recovery:**
1. Receiving specialist's compliance check catches it and returns the packet with a flag.
2. Orchestrator re-runs the compliance scan with the flagged input.
3. Routes to escalation chain (broker, Diana, title).

**Architectural protection:** Every specialist runs their own compliance check on incoming packets. Defense in depth.

### Ambiguous request can't be classified

**What happens:** A request like "Help me with the Williams" with no other context.

**How it surfaces:** Orchestrator cannot pick a specialist.

**Recovery:** Orchestrator asks one clarifying question: "Is this about a new lead, property research, drafting a message, or a live transaction with the Williams?" Does not guess.

**Architectural protection:** The orchestrator's `rules.md` requires classification before routing.

## 01_lead_qualifier Failure Modes

### Lead temperature mis-assigned

**What happens:** Qualifier marks a `Hot` lead as `Warm`, or vice versa. Downstream urgency mismatches reality.

**How it surfaces:** Team member sees the temperature in the lead summary, disagrees.

**Recovery:**
1. Team member says: "This is actually hot, the buyer wants to tour Saturday."
2. Qualifier re-assigns and re-runs the next-action recommendation.
3. Handoff packet is updated.

**Architectural protection:** Lead temperature is visible in the lead summary output, not hidden. Team member can override before the packet goes to the next specialist.

### Buyer rep agreement gate missed

**What happens:** Qualifier produces a "recommend a Saturday showing" recommendation without confirming the buyer rep agreement is signed.

**How it surfaces:** The `03_client_communication` packet would draft a showing invitation, but the architecture has this check at TWO layers — qualifier rules AND 03's draft-time check.

**Recovery:**
1. If 01 misses: 03 catches it during draft compliance check. Returns packet to orchestrator with rep-agreement requirement noted.
2. Orchestrator pauses, asks team member if rep agreement is signed, or asks 01 to re-qualify.

**Architectural protection:** Two-layer compliance check (qualifier + draft-time). The post-NAR requirement is reinforced in both `01_lead_qualifier/rules.md` and `01_lead_qualifier/reference/first-contact-playbook.md`.

### Fair-housing-sensitive language slips in

**What happens:** A lead says "we want a neighborhood that's good for families" and the qualifier accidentally includes "family-friendly" in the lead summary.

**How it surfaces:** The downstream specialists either propagate the error OR catch it. `02_property_research/rules.md` and `03_client_communication/rules.md` both explicitly flag this language.

**Recovery:**
1. Receiving specialist returns packet with fair-housing flag raised.
2. Orchestrator re-runs the request with the flag and routes back through qualifier with explicit "use client-defined criteria only" instruction.
3. Re-drafted output uses commute, walkability, lot size, etc., instead of demographic proxies.

**Architectural protection:** Fair-housing rules in every specialist, not just the qualifier. Multiple chances to catch.

## 02_property_research Failure Modes

### Source can't be verified

**What happens:** The team-approved MLS is down, the county records site is slow, or the listing has been pulled and there's no replacement source.

**How it surfaces:** Research output cannot have a Source-checked-at timestamp.

**Recovery:** Research specialist explicitly labels every fact as `unverified` or `source pending`. Refuses to produce a client-ready takeaway until at least one source is verified. Handoff packet to `03_client_communication` is marked `Needs source verification` and the draft must include caveats.

**Architectural protection:** Source-of-truth and Source-checked-at are required fields in the handoff packet. No verified source = no high-confidence claim.

### Conflicting sources

**What happens:** Listing says 3 bedrooms; county records say 2. Listing says 1980; tax records say 1976.

**How it surfaces:** Research output shows the conflict.

**Recovery:** Research specialist surfaces both data points with their sources. Does NOT pick one. Routes to Diana or human escalation to resolve.

**Architectural protection:** Source confidence per fact. Conflicting sources flag automatically.

### Fair-housing question disguised as research

**What happens:** Team member asks "research whether this neighborhood is good for families."

**How it surfaces:** Research specialist rejects the framing in its output.

**Recovery:** Research specialist re-frames: "I won't research a neighborhood's suitability for a protected class. I CAN research commute times, school district boundaries (objective, not quality rankings), walkability scores, lot sizes, recent comp activity, and neighborhood-specific permit/zoning history. Which of those would help?"

**Architectural protection:** Compliance rules in `02_property_research/rules.md` block protected-class characterizations.

## 03_client_communication Failure Modes

### Voice drift

**What happens:** Draft sounds generic, not like Diana. Voice score comes in at 12/20.

**How it surfaces:** Voice score is part of the output. Below 15 means rewrite before review.

**Recovery:**
1. System auto-revises before showing the draft to Diana, if voice score is below threshold.
2. If still off, team member can say "the voice is off, make it sharper / warmer / shorter" and the system re-drafts.
3. If consistently off, that signals the synthetic Diana voice is still in place. Run `support/setup/voice-onboarding.md` to replace it.

**Architectural protection:** Voice score is a required output, calibrated against Diana's profile.

### Wire instructions request

**What happens:** Team member asks the system to draft "send the buyer the new wire instructions."

**How it surfaces:** System refuses.

**Recovery:** System produces a response that explains it cannot relay wire instructions, names the wire-fraud risk, and offers to draft a "call title to verify" message instead. Routes back to orchestrator with wire-fraud risk flag raised.

**Architectural protection:** Hard never-rule in `../../03_client_communication/rules.md` AND `../../04_transaction_coordinator/rules.md`. Defense in depth. Demonstrated in [`scenarios/05-wire-fraud-attempt.md`](scenarios/05-wire-fraud-attempt.md).

### Auto-translation request

**What happens:** Team member asks the system to draft a message in Spanish for a Spanish-preferring client.

**How it surfaces:** System refuses.

**Recovery:** System produces an English draft, flags the language preference for handoff, and recommends routing to a bilingual team member or certified translator. Real estate translation has legal weight an AI shouldn't carry unsupervised.

**Architectural protection:** Language rule in `03_client_communication/rules.md`.

## 04_transaction_coordinator Failure Modes

### Date conflicts with executed contract

**What happens:** Team member says "option ends Friday." Contract effective date suggests it ends Thursday.

**How it surfaces:** Transaction coordinator marks the deadline as `unverified`.

**Recovery:** Coordinator's output explicitly flags: "Team member said Friday, contract math suggests Thursday. Please verify against executed contract before any client communication uses either date." Does not pick one.

**Architectural protection:** Source-of-truth field in handoff packet. Date verification is a hard requirement in `04_transaction_coordinator/rules.md`.

### Inspection severity claim

**What happens:** Team member asks "tell the buyer the foundation cracks aren't a big deal."

**How it surfaces:** Coordinator refuses to characterize severity.

**Recovery:** Coordinator produces structure (inspector said X, structural engineer should evaluate before any severity claim, four buyer paths) but not a recommendation. Demonstrated in [`scenarios/04-inspection-crisis.md`](scenarios/04-inspection-crisis.md).

**Architectural protection:** Inspection-renegotiation playbook explicitly rejects severity-claim language.

### Post-option termination request

**What happens:** Buyer wants to back out after the option period ended.

**How it surfaces:** Coordinator flags as broker/attorney escalation.

**Recovery:** Coordinator does NOT draft a termination message. Routes to broker and possibly attorney. Surfaces what's at stake (earnest money, potential default).

**Architectural protection:** Mandatory escalations are listed in `04_transaction_coordinator/reference/texas-trec-checklist.md`.

## Cross-Cutting Failure Modes

### Stale memory across chats

**What happens:** A new chat doesn't remember what the previous chat established about the same client.

**How it surfaces:** System asks for context that was already given.

**Recovery:** Team member pastes the current lead/deal log or prior handoff packet into the new chat. The system treats each chat as a fresh start and updates the log before the work continues.

**Architectural protection:** This is a known limitation of the no-software human-paste model. The richer lead/deal log template and Deal Desk brief give the team a pasteable state layer without turning the project into software. A future v2 could persist packets as JSON files for re-loading, but v1 keeps them in-chat.

### Deal Desk shows stale or missing state

**What happens:** A daily brief cannot tell what matters because a lead/deal log is missing a next owner, next check date, or latest handoff.

**How it surfaces:** The Deal Desk puts the matter under `Stale Or Waiting` or `Cannot Move Until`.

**Recovery:** Update the lead/deal log with current status, owner, open action, latest handoff metadata, and next check date before making decisions from the brief.

**Architectural protection:** `support/reference/deal-desk.md` only uses current logs and handoff packets. It does not invent state from old chat memory.

### Hallucinated facts

**What happens:** The underlying AI makes something up about the property, market, or contract.

**How it surfaces:** Every fact has a source field in the packet. Hallucinated facts have empty or vague sources.

**Recovery:** Team member or downstream specialist catches the missing source and routes back. Diana's review is the final gate.

**Architectural protection:** Source-of-truth required for every fact. Voice score and `Needs source verification` labels. Human review on every client-facing draft.

### Adversarial / bad-faith user

**What happens:** A team member tries to rephrase a fair-housing question to slip past compliance, or asks the system to draft a misleading client message.

**How it surfaces:** Compliance scan catches the rephrase, OR the receiving specialist catches it at draft-time.

**Recovery:** System refuses, explains why, offers a compliant alternative. If the pattern repeats, escalate to broker.

**Architectural protection:** Defense in depth — compliance is checked at the orchestrator AND at each specialist. A single rephrase doesn't bypass both layers.

## What These Failure Modes Reveal

The Agency is designed assuming:

1. The AI will sometimes route wrong.
2. The AI will sometimes hallucinate.
3. The team member will sometimes ask for things that violate compliance.
4. Sources will sometimes be unavailable.
5. Voice will sometimes drift.

For each, the architecture has a recovery path that does not require trusting the AI to be perfect. The handoff packet is the unit of accountability, the lead/deal log is the state layer, and the Deal Desk is the daily operating view.

That is the difference between a system designed for happy-path demos and a system designed to survive contact with reality.
