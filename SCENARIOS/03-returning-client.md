# Scenario 03: Returning Client

Past client reaching back out. Tests the `modes/returning.md` lighter-touch intake and welcome-back tone.

## Raw Request

```text
Hey, just got a text from Mike and Lily Romero — we sold them their place in Bouldin in 2022. They're back. Twins on the way, need more space. Same East Austin area but up to 900k now. Mike said they're "thinking out loud" but timing is real because the babies are due in March.
```

## Routing Decision (00_orchestrator)

Sequence: `01_lead_qualifier` (returning mode) → `03_client_communication`.

**Why.** Returning clients get a much lighter intake than fresh leads. The relationship is established; the qualifier needs to acknowledge the prior history, capture what changed, and surface a warm welcome-back response. Property research is not needed yet — they're still in "thinking out loud" territory.

**Compliance scan:**
- Fair housing: low. Note: "twins on the way" reveals familial status, which is a protected class. Do NOT use it in any client-facing copy or in routing decisions. Capture timeline ("babies due in March") without referencing family composition.
- Advertising or broker-review: low.
- Buyer rep agreement: their previous agreement may have lapsed. Confirm a new one is signed before any showing.
- Returning client signal: STRONG. Route to `01/modes/returning.md`, not the standard new-lead intake.

## Handoff Chain

### Packet 1: 00 → 01

```md
From: 00_orchestrator
To: 01_lead_qualifier (returning mode)
Matter ID: MOCK-RETURN-003
Stage: Returning client re-intake
Client or lead: Mike and Lily Romero
Matter: Past clients exploring an upsize move
Urgency: Medium, real timeline of March

## Prior Relationship
- Sold them their Bouldin home in 2022.
- Diana was the listing agent on their purchase.

## Pre-known Data
- Same East Austin area preference.
- Budget up to 900k.
- Need more space.
- Timeline driven by March family event.
- "Thinking out loud" phrasing — not fully committed yet.

## Sensitive Detail (DO NOT use in client copy)
- The reason for the move is a family addition. Treat as protected-class information; use the timeline only, never the cause, in any drafts or notes.

## Missing Information
- Blocking: do they want to buy first, sell first, or do both at once?
- Helpful: ideal move date, what "more space" means specifically.

## Requested Output
Returning-client re-intake summary (3 questions max), welcome-back tone, handoff to client communication.
```

### Packet 2: 01 → 03

```md
From: 01_lead_qualifier
To: 03_client_communication
Matter ID: MOCK-RETURN-003
Stage: Welcome-back message + light intake invite
Client or lead: Mike and Lily Romero
Matter: Draft a warm welcome-back text + email, propose a casual call
Urgency: Medium

## Lead Summary
Returning clients (sold them their Bouldin home in 2022). Now exploring an upsize, same East Austin area, up to 900k. Real timeline of March. "Thinking out loud" — not fully committed.

## Lead Temperature
Warm (returning clients skew warmer by default).

## Recommended Tone
Welcome-back, no agenda, low pressure. Acknowledge the gap. Don't refer to family additions or the reason for the move; use the timeline only.

## Suggested Channels
- Text first (Mike texted Diana directly).
- Follow up with email if no response in 24 hours.

## Compliance Flags
- Fair housing: HIGH SENSITIVITY for client-facing copy. Do NOT mention or imply the family-composition reason for the move. Use timeline-only language.
- Buyer rep agreement: prior agreement may have lapsed. Frame the new rep conversation as a routine refresher, not a hurdle.

## Source And Proof State
- Source of truth: Mike's text + Diana's prior client record.
- Proof: prior transaction record in deal file.

## Requested Output
Two drafts: (a) text reply, (b) email follow-up. Both warm, both low-pressure, both surface the rep-agreement refresh casually.

## Human Review
- Reviewer needed: Diana.
- Review reason: returning client, welcome-back tone matters, fair-housing sensitivity around move reason.
- Cannot proceed until: Diana approves both drafts.
```

## Final Output (drafted by 03_client_communication)

**Draft Status:** Needs Diana review.

**Voice Score:** 19/20.

### Draft A — Text

> Hey Mike — great to hear from you. Excited to help. I'd love to hear what you and Lily are thinking. Want to do a quick call this week? 15 min, no agenda. Wednesday afternoon or Thursday morning work for me. — Diana

### Draft B — Email follow-up (send if no text reply in 24 hours)

> Subject: Great to hear from you
>
> Hi Mike and Lily,
>
> Great to hear from you. I think about the Bouldin place often, hope it's been treating you well.
>
> When you're ready to start the next chapter — even just thinking out loud — I'd love a quick call to hear what you have in mind. March is a real timeline, so we have room to be thoughtful but not unlimited room.
>
> A few quick housekeeping notes when we talk:
>
> - For buying side, we'll do a quick refresher on the buyer's representation agreement. Routine, takes about 15 minutes.
> - If you're thinking about selling the Bouldin place too, I'll bring some thoughts on the timing — that market has shifted some since 2022.
>
> Whenever you want to chat: Wednesday afternoon and Thursday morning are open this week. Pick whichever fits or grab another time and I'll work around it.
>
> Diana

**Human Review Notes:**
Neither draft references the family composition reason for the move. The timeline ("March") is used as-is. The rep agreement refresher is framed casually as routine. Diana should confirm tone matches her usual returning-client voice before sending.

## What This Demonstrates

- **The modes/ pattern routes intake style based on lead type.**
- **Returning clients get 3 questions max, not the full new-lead intake.**
- **Fair-housing protection is active even when the protected-class info is shared willingly by the lead.**
- **The compliance filter catches sensitivity that a non-trained system would copy into the reply.**
- **Welcome-back tone is preserved through voice score + human review.**
- **The rep agreement requirement is surfaced as routine, not as friction.**
