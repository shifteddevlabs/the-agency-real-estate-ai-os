# Mode: New Lead Intake

Triggered when the orchestrator passes `lead_type: new`. Use this scripted default flow when no channel-specific playbook in `reference/first-contact-playbook.md` applies, or when the user just wants the standard intake.

## Pre-intake check

Before asking any questions, scan the user's original message and any pasted content for fields you can fill in already. The orchestrator passes `pre_known_data` with anything Diana volunteered upfront. Don't re-ask for things you already know.

## The intake (one question at a time)

Ask only the questions you don't already have answers to. Skip any that are pre-filled. Keep the count visible: "Question 3 of 6" feels finite to the user.

### Q1, Name and contact
> "Got a new lead, let's get them captured. **Question 1 of 6.** What's their name and best way to reach them (phone, email, or both)?"

### Q2, Source
> "**Question 2 of 6.** Where did this lead come from? Zillow, referral, your website, an open house, a sphere intro?"

### Q3, Buy or sell
> "**Question 3 of 6.** Are they looking to buy, sell, or both?"

### Q4, Motivation
> "**Question 4 of 6.** Why now? Even a one-line answer is fine. Job change, space needs, downsizing, investment, just curious."

### Q5, Timeline
> "**Question 5 of 6.** What's their timeline? 'Immediately,' '30 to 60 days,' 'spring 2027,' or 'just exploring' all work."

### Q6, Buyer-specific OR seller-specific (branch here)

**If buyer:**
> "**Question 6 of 6 (last one).** Two parts: what's their price range, and are they pre-approved? (Yes / no / working on it / don't ask is also fine.)"

**If seller:**
> "**Question 6 of 6 (last one).** What's the property? Address if you have it, plus a quick read on condition and whether anyone's living there now."

**If both:**
> "**Question 6 of 6 (last one).** For the buy side, what's their price range and pre-approval status? For the sell side, what's the property?"

### Optional Q7, Geography (only if not already clear)

> "Last thing, what areas or ZIP codes are they interested in? Skip if you don't know yet."

## Generate the Lead Summary

Use the format from `rules.md`. Fill in every field you have. Mark unknowns clearly.

## Set temperature

Use this rough heuristic. Override based on what Diana clearly intends. Temperature scale must match `rules.md` (Hot / Warm / Nurture / Unqualified).

- **Hot:** Pre-approved, 0 to 30 days, motivated (relocation, divorce, baby on the way, etc.)
- **Warm:** Pre-approved or actively getting there, 30 to 90 days, clear motivation
- **Nurture:** No pre-approval, 90+ days, exploratory motivation, OR no timeline / casually browsing, OR 6+ months out but real intent (e.g., relocating in fall)
- **Unqualified:** Outside scope, unreachable, unrealistic for the team's service area, or already represented

## Recommend next action

Pick one and write it as a single sentence.

- Hot → "Reply within 1 hour. Draft a first-reply email now."
- Warm → "Reply today. Draft a first-reply email or text, schedule a call this week."
- Nurture → "Light touch. Add to standard buyer/seller drip or general newsletter. Personal note this week if engagement is real, or schedule a check-in note for the estimated month if it's a longer timeline."
- Unqualified (out-of-market) → "Refer out. Hand to client communication for a referral letter."
- Unqualified (already represented) → "Polite boundary reply. Hand to client communication for a respectful reply that does not interfere with their existing agent."

## Surface and offer

Surface the Lead Summary in chat. Then say:

> "Here's the lead summary. Want me to:
> 1. Save this as a file you can paste into your CRM
> 2. Draft a first-reply [email / text] right now
> 3. Both"

Wait for the user's pick. Don't proceed automatically.

## Related references

- See `01_lead_qualifier/examples.md` for end-to-end intake examples by channel.
- See `01_lead_qualifier/reference/first-contact-playbook.md` for channel-specific first-reply scripts (website form, portal inquiry, referral, open house, seller, just-browsing, already-represented).
