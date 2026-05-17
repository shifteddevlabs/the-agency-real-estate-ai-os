# First-Contact Playbook

Use this playbook for first replies to real estate leads. The goal is to make the lead feel heard, collect only the facts the team needs, assign lead temperature, and prepare a clean handoff for the next owner.

This document uses placeholders only. Do not add real client data, private notes, credentials, or secrets.

## Core Workflow

1. Identify the channel and source.
2. Acknowledge the lead's request in one friendly sentence.
3. Ask 2 to 4 natural intake questions.
4. Confirm representation status before giving substantive guidance.
5. Assign lead temperature: `Hot`, `Warm`, `Nurture`, or `Unqualified`.
6. Prepare a handoff packet if a human or another capability should take over.

For message quality, use `03_client_communication/reference/sales-psychology-baseline.md`: acknowledge the concern, ask only useful questions, lower the stakes, and end with one easy next step.

## Lead Enrichment Policy

Default: enrich the request, not the person.

For first contact, the useful enrichment is usually:

- What source did the lead come from?
- What property, area, budget, or timeline did they mention?
- Are they represented?
- What is the next consent-based reply?
- What facts need verification before a response?

Do not use people-search, skip-tracing, email-finder, or personal-data enrichment tools for consumer leads unless Diana's brokerage has approved the workflow, consent rules, and privacy policy.

Norbert-style enrichment can be useful for business outreach, but it is not the default for residential real estate leads. Most residential first-contact work should rely on submitted information, referral context, CRM history, and the lead's own answers.

Allowed enrichment:

- Team CRM history.
- Submitted form fields.
- Referral context the referrer was allowed to share.
- Property or listing status from approved real estate sources.
- Public source categories for property research, handled by `02_property_research/`.

Not allowed by default:

- Guessing missing email addresses.
- Pulling personal phone numbers from third-party data brokers.
- Scraping social profiles.
- Adding sensitive personal, family, financial, or hardship details to handoffs.
- Using enrichment to pressure a distressed seller or buyer.

## Required Intake Fields

Capture only what is needed for the next step.

### All Leads

- Name.
- Best contact method.
- Preferred language: English / Spanish / other.
- Source or channel.
- Lead type: buyer, seller, renter, investor, referral, open house, portal inquiry, nurture.
- Current agent relationship.
- Desired next step.
- Timeline.
- Budget, price range, or comfort range if volunteered or needed.
- Areas, addresses, or property types named by the lead.
- Blocking missing information.
- Human review needed: yes or no.

### Buyers

- Buying purpose: primary home, second home, investment, relocation, or other.
- Financing status: pre-approved, cash, exploring, unknown.
- Must-haves.
- Deal breakers.
- Tour readiness.
- Preferred appointment windows.
- **Buyer representation agreement status: signed / in-progress / not started.** Required before any home showing (NAR 2024 settlement, see section below).

### Sellers

- Property address.
- Ownership or decision-maker status.
- Desired sale timeline.
- Reason for exploring a sale, only if volunteered or gently asked.
- Property condition, updates, or known issues.
- Occupancy status.
- Whether they want a pricing consult, prep advice, or listing timeline.

### Renters

- Move date.
- Monthly budget comfort.
- Bedrooms or property type.
- Pets, parking, accessibility needs, or other requirements only if volunteered or relevant.
- Application readiness.

### Investors

- Investment goal.
- Asset type.
- Target area or criteria.
- Budget or financing.
- Experience level.
- Return criteria if volunteered.

## Lead Temperature

- `Hot`: wants action now, has a clear timeline, is reachable, and is ready for a tour, consult, or appointment.
- `Warm`: real intent, but key details are missing or timing is not immediate.
- `Nurture`: early research, longer timeline, browsing, or needs education before taking action.
- `Unqualified`: unreachable, outside scope, unrealistic for the team's service area, unsafe, spam, or already represented in a way that blocks engagement.

## Channel-Specific First Replies

### Website Form

Use when the lead submits a contact form, valuation form, buyer form, or general inquiry.

First reply:

> Hi [First Name], thanks for reaching out through the website. I can help route this to the right person on the team. Are you looking to buy, sell, rent, invest, or just ask a general question?

Follow-up questions:

- What timeline are you working with?
- What area, address, or property type should we focus on?
- Are you already working with an agent?
- What would be the most helpful next step: a quick call, property research, a showing request, or a seller consult?

Likely temperature:

- `Hot` if they ask for an appointment, showing, valuation, or immediate help.
- `Warm` if they give intent but not timing.
- `Nurture` if the request is informational only.

Handoff hints:

- Route to Client Communication if the next step is a reply or call invite.
- Route to Property Research if they name areas, addresses, or criteria.
- Add `Blocking` for missing lead type, representation status, or contact method.

### Zillow/Realtor-Style Portal Inquiry

Use only when the team receives a lead submitted through a portal-style inquiry or manually provided lead text. Do not scrape portals, imply API access, or claim current listing status unless the team has independently verified it.

First reply:

> Hi [First Name], thanks for asking about [Property Address or Listing]. I can help get this to the team. Are you hoping to tour it, ask a question about it, or compare similar options?

Follow-up questions:

- Are you already represented by an agent?
- What timing are you hoping for on a tour or next step?
- Are you pre-approved, paying cash, or still exploring financing?
- If this property is no longer available, would you like the team to look for similar options using your criteria?

Likely temperature:

- `Hot` if they request a tour soon and are reachable.
- `Warm` if they like the property but have not confirmed timing or financing.
- `Nurture` if they are casually browsing.
- `Unqualified` if they are represented and seeking advice that should go through their agent.

Handoff hints:

- Include the exact property address or listing reference provided by the lead.
- Mark listing availability as `Needs human verification`.
- Do not promise availability, price, seller terms, or access.

### Referral Text

Use when someone sends a text such as "My friend [Name] is looking to buy" or "[Name] said to reach out."

First reply to referral source:

> Thanks for the intro. I will keep it simple and respectful. What is the best contact info for [Lead First Name], and did they say whether they are buying, selling, renting, or investing?

First reply to referred lead:

> Hi [First Name], [Referral Source] suggested I reach out. No pressure at all, I just want to understand what kind of help would be useful. Are you looking to buy, sell, rent, invest, or just gather information right now?

Follow-up questions:

- What timeline are you thinking about?
- Are you already working with an agent?
- What area, property type, or goal should the team know about?
- Would a quick call or a short text follow-up be easier?

Likely temperature:

- `Warm` by default if the referral source is credible but intent is not confirmed.
- `Hot` if the referred lead confirms immediate need.
- `Nurture` if they are researching.

Handoff hints:

- Preserve referral source name if allowed.
- Note whether permission to contact was explicit, implied, or unclear.
- If permission is unclear, keep outreach minimal and route for human review.

### Open House Follow-Up

Use after an open house sign-in, conversation note, or post-event follow-up.

First reply:

> Hi [First Name], thanks for stopping by the open house at [Property Address]. I wanted to follow up while it is fresh. Are you interested in that home specifically, or was it more helpful as a reference point for your search?

Follow-up questions:

- Are you already working with an agent?
- What did you like or not like about the home?
- What areas, price range, or property features should the team keep in mind?
- Are you hoping to tour more homes soon, or are you still getting oriented?

Likely temperature:

- `Hot` if they want a second showing, offer discussion, or immediate search help.
- `Warm` if they shared criteria and are open to follow-up.
- `Nurture` if they are early-stage or comparing neighborhoods on their own terms.

Handoff hints:

- Include property address, event date if known, and any volunteered preferences.
- Do not infer protected-class details from appearance, companions, or conversation.
- Route offer questions, pricing strategy, or agency questions to a licensed human.

### Seller Inquiry

Use when the lead asks about selling, home value, listing timing, or property preparation.

First reply:

> Hi [First Name], thanks for reaching out about selling. I can help the team understand the basics before they follow up. What property address are you considering, and are you looking for a value estimate, a listing timeline, or prep guidance?

Follow-up questions:

- Are you the owner or one of the decision-makers for the property?
- What timeline are you considering?
- Is the property occupied, vacant, tenant-occupied, or unknown?
- Have there been any major updates or known condition issues the team should know about?
- Are you already speaking with another agent about listing it?

Likely temperature:

- `Hot` if they want a consult, valuation, or listing timeline soon.
- `Warm` if they are considering a sale but timing is flexible.
- `Nurture` if they only want periodic market updates.

Handoff hints:

- Route to Client Communication for a seller consult invite.
- Route to Property Research for property facts, comps, and objective prep questions.
- Mark value, pricing, and listing strategy as `Licensed human review required`.

### Just-Browsing Nurture Lead

Use when the lead says they are "just looking," "not ready," "maybe next year," or similar.

First reply:

> Totally fine, [First Name]. I can keep this low-pressure. What would make future updates useful: price changes, homes in a specific area, market snapshots, or occasional check-ins?

Follow-up questions:

- Is there a rough timeframe you have in mind, even if it is flexible?
- What areas or property types are you curious about?
- Would monthly, quarterly, or no scheduled follow-up be best?
- Are you already working with an agent?

Likely temperature:

- `Nurture` unless they reveal a near-term trigger.
- `Warm` if they share a clear future timeline and criteria.

Handoff hints:

- Do not pressure the lead or create fake urgency.
- Capture follow-up cadence and content preference.
- Route to Client Communication for a nurture note or drip setup.

### Already-Represented Lead

Use when the lead says they have an agent, are under an agreement, or are asking for advice about a transaction already handled by another agent.

First reply:

> Thanks for letting me know. Since you are already working with an agent, the best next step is usually to keep questions about specific properties, offers, or strategy with them. I can make a note here and route this for review if there is a general question the team can answer appropriately.

Follow-up questions:

- Are you looking for general public information, or help that should go through your agent?
- Is there anything you want the team to review before deciding whether a response is appropriate?
- Would you like us to pause follow-up while you are represented?

Likely temperature:

- `Unqualified` if the request would interfere with an existing agent relationship.
- `Nurture` only if the lead asks for future contact after their current representation ends.
- `Warm` only after a human confirms contact is appropriate.

Handoff hints:

- Mark `Human Review` as yes.
- Do not advise the lead to break, avoid, or work around a representation agreement.
- Do not provide offer strategy, pricing strategy, showing guidance, or negotiation advice.

## Plug-And-Play Question Bank

Use these when the channel does not fit a specific script.

- What kind of help would be most useful right now?
- What timeline are you working with?
- Are you already working with an agent?
- What area, address, or property type should the team focus on?
- What is your comfortable budget or price range?
- Are you pre-approved, paying cash, or still exploring financing?
- What are your must-haves?
- What would rule a property out?
- Would you prefer a call, text, or email follow-up?
- Is there anything the team should avoid assuming?

## Handoff Packet Template

Use this format when routing the lead to another owner.

```md
## Lead Summary

## Lead Temperature

## Known Facts

## Missing Information

### Blocking

### Helpful

## Recommended Next Action

## Suggested Follow-Up Questions

## Handoff Packet

- Matter ID:
- Stage:
- Source of truth:
- Lead source/channel:
- Lead type:
- Representation status:
- Reviewer needed:
- Review reason:
- Cannot proceed until:
- Human Review:
```

## Handoff Packet Hints

- Client Communication: use for reply drafts, call invites, meeting scheduling, nurture follow-up, and tone-sensitive outreach.
- Property Research: use for addresses, property facts, client-defined criteria, market context, and objective comparison questions.
- Transaction Coordinator: use only after representation, appointment, contract, or transaction status has been verified by a human.
- Orchestrator: use when ownership is unclear, the request mixes departments, or compliance risk is high.

## Buyer Representation Agreement (Post-NAR 2024)

The NAR class-action settlement (Sitzer/Burnett, effective August 2024) changed how buyer's agents engage with leads.

**Two new requirements:**

1. Buyer's agents must have a signed written representation agreement with a buyer BEFORE showing any home. Even one home. No exceptions.
2. Buyer commission is now negotiated directly with the buyer (the seller no longer assumes the buyer-agent commission by default).

**How this changes lead qualification:**

- Capture buyer rep agreement status during intake. Do NOT skip this field for buyer leads.
- If a buyer has not signed a rep agreement with Diana's team, the recommended next action is a buyer consult to discuss representation and sign the agreement, NOT a home showing.
- If a buyer has signed a rep agreement with another agent, mark the lead `Unqualified` for now. Note for re-engagement after that representation ends.
- If a buyer asks for a showing before any agreement is in place, explain plainly: "Before we tour homes together, we need to sign a buyer representation agreement that explains how my services work and how I get paid. It usually takes 15 minutes. Want me to set up a quick consult this week?"

**In Texas:**

- The most common form is TXR-1501 (TAR Residential Buyer/Tenant Representation Agreement).
- TREC IABS (Information About Brokerage Services) form is required at first substantive communication.
- Terms vary: exclusive vs. non-exclusive, duration, geographic scope, compensation structure.

**Edge cases:**

- Open house attendees: the open house itself does not require individual buyer rep. But any follow-up showing of any property does.
- Cooperating buyers (showing Diana's listing to a buyer represented by another agent): the other agent's representation agreement is their compliance, not ours. Verify it exists, then proceed.
- Buyer rep signed before NAR rules changed: check whether re-execution is needed. Escalate to broker if unclear.

## Language Handling

The Agency drafts in English only. Austin metro is roughly 33% Hispanic, and Spanish-speaking leads enter the pipeline regularly.

**For non-English-preferring leads:**

1. Capture the language preference at intake (added to "All Leads" required fields).
2. Surface a handoff flag for Diana: "This lead requested [language]. Route to [Diana's bilingual team member if any] or arrange a certified translator for written materials."
3. Do NOT generate non-English client communication from this system. Translation of real estate documents has legal weight beyond what an AI should produce unsupervised.
4. For verbal conversations, Diana's team can use a bilingual team member or a phone-based interpreter service.

The system does not block these leads; it surfaces them so the right human can take the next step. If Diana's team is monolingual, this is a referral-out scenario, not a workflow-blocker.

## Compliance Guardrails

- Do not ask about race, color, national origin, religion, sex, familial status, disability, or other protected-class traits.
- Do not steer leads toward or away from neighborhoods based on who they are.
- Do not answer whether an area is safe, good for families, or right for a protected group. Offer objective sources or client-defined criteria instead.
- Do not imply legal, tax, mortgage, inspection, appraisal, or insurance advice.
- Do not promise property availability, pricing, valuation, approval, outcome, or access.
- Do not claim MLS, portal, CRM, email, or API access unless that access is actually available in the current workflow.
- Do not scrape websites or portals for lead data.
- Do not store unnecessary sensitive personal data.
- Do not contact a represented lead about matters that should go through their current agent without human review.
- Escalate threats, harassment, discrimination requests, fraud concerns, or unusual financial requests immediately.

## Final Output Checklist

Before handing off, confirm:

- Lead source is identified.
- Representation status is captured or marked missing.
- Lead temperature is assigned with a reason.
- The next action is clear.
- Blocking missing information is listed.
- Compliance risks are noted.
- Human review is marked yes when required.
