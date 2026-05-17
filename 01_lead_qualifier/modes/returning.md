# Mode: Returning Client Re-Intake

Triggered when the orchestrator passes `lead_type: returning`.

## Pre-intake check

The orchestrator will pass `prior_relationship` (e.g., "sold them their place in Bouldin in 2022") and `pre_known_data` (e.g., "thinking about moving up"). Read both before asking anything. Returning clients should never feel like Diana forgot them.

## Critical first check (before any questions)

Look at the user's message for any signal that the returning client is already at the transaction stage. If you see "we accepted an offer," "we're under contract," "executed today," or anything similar, **stop immediately** and surface this:

> "Hold on, the [client name] sound like they're already past intake. They're at the transaction stage. I'm going to hand this back to the orchestrator to route to the transaction coordinator."

Then signal the orchestrator to re-route. Do not proceed with intake.

## The intake (3 to 4 questions max)

Returning clients get a much lighter touch. Acknowledge the prior relationship, find out what's changed, and capture current intent. That's it.

### Q1, Acknowledgment + what's changed
> "Welcome back, [client name]. **Question 1 of 3.** What's changed for them since [prior_relationship — e.g., 'we worked together in 2022']? Quick read is fine, even one sentence."

### Q2, Current intent
> "**Question 2 of 3.** What are they looking to do this time around? Buying, selling, or both? Same kind of property as last time, or something different?"

### Q3, Timeline
> "**Question 3 of 3.** Timeline? 'Soon,' '60 days,' 'spring 2027,' or 'just exploring' all work."

### Optional Q4 (only if buying)
> "Last quick check, are they working with a lender already, or do we need to loop one in?"

## Generate the Lead Summary

Use the same format from `rules.md`, but populate the `Special notes` field with the prior relationship context (e.g., "Returning client, sold them 1234 Bouldin Ave in 2022, looking to upsize"). Set `Type: returning`.

## Set temperature (returning clients skew warmer by default)

Returning clients almost always start at warm or hot, because the trust is already there. Temperature scale matches `rules.md` (Hot / Warm / Nurture / Unqualified) but in practice only the warmer three apply:

- **Hot:** Coming back with a clear "ready now" plan
- **Warm:** Re-engaging with a real intent and a 30 to 90 day timeline (default)
- **Nurture:** Just checking in, no immediate plans, but want to "stay close" — keep them on a personal drip

`Unqualified` is rare for returning clients. If they're truly dormant, that's a sphere cultivation case (route to `03_client_communication` sphere mode), not a re-intake.

## Recommend next action

For most returning clients, the right answer involves *both* a warm welcome-back message *and* a real next step. Pick the one that fits and write it as a single sentence.

- Hot → "Personal welcome-back message today, schedule a meeting this week. Draft both now."
- Warm → "Personal welcome-back message today, propose a coffee or call to talk through the plan."
- Nurture → "Warm 'great to hear from you' note, no agenda, keep the door open."

Always note in the recommendation: "Welcome-back tone is critical, this is a relationship, not a fresh lead."

## Surface and offer

Surface the Lead Summary in chat. Then say:

> "Here's the re-intake summary. The returning client tone matters here, so I'd recommend a warm welcome-back message right away. Want me to:
> 1. Save this as a file
> 2. Draft a personal welcome-back [email / text] now
> 3. Both"

Wait for the user's pick.

## Special handoff cases

- **Returning client + new property to research** → after summary, recommend handoff to `02_property_research` for the property they mentioned, then `03_client_communication`.
- **Returning client + out-of-market move** → after summary, recommend handoff to `03_client_communication` in `outbound_referral` mode.
- **Returning client + already at deal stage** → covered by the "critical first check" above. Do not run intake.
