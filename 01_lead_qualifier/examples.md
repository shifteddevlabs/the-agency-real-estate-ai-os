# Examples

Use these as plug-and-play first-contact patterns. Keep replies short, useful, and compliant. The lead qualifier does not send messages directly unless Diana asks. It prepares the intake summary and hands the draft request to `03_client_communication/`.

## Example 1, Website Buyer Form

Input:

```text
Website form: "Moving to Austin this summer. Looking around 700k to 800k, maybe East Austin. I work downtown and want something with character."
```

Output:

```md
## Lead Summary
Buyer relocating to Austin this summer. Budget comfort appears to be 700k to 800k. Downtown commute and older or character property matter.

## Lead Temperature
Warm

## Known Facts
- Source: website form.
- Moving to Austin this summer.
- Budget comfort: 700k to 800k.
- Work anchor: downtown.
- Preference: home with character.

## Missing Information
- Blocking:
  - Financing or pre-approval status.
  - Current agent relationship.
- Helpful:
  - Exact move date.
  - Property type, bedrooms, parking, outdoor space.
  - Preferred communication channel.
- Can wait:
  - Showing availability.

## Recommended Next Action
Ask three questions and offer a 15-minute buyer consult.

## Suggested Follow-Up Questions
1. Are you already pre-approved or still choosing a lender?
2. Are you currently working with another agent?
3. What are your must-haves besides staying within that price range?

## Handoff Packet
From: `01_lead_qualifier`
To: `03_client_communication`
Matter ID: `MOCK-LEAD-WEB-001`
Stage: First response draft
Client or lead: Website buyer lead
Matter: Buyer relocation inquiry
Urgency: Medium
Current status: Warm lead, needs qualification reply

## Compliance Flags
- Fair housing: low, keep location discussion objective and client-led.
- Legal, tax, lending, or inspection advice: medium, financing questions go to lender.
- Privacy or sensitive data: low, do not add personal details beyond intake needs.

## Human Review
- Reviewer needed: Diana or assigned agent.
- Review reason: first client-facing reply.
- Cannot proceed until: Diana approves message tone and call-to-action.
```

## Example 2, Portal Inquiry

Input:

```text
Portal inquiry: "Is 4812 Sample Bend still available? We could see it this weekend."
```

Output:

```md
## Lead Summary
Buyer lead asking about a specific property and a possible weekend showing.

## Lead Temperature
Hot if reachable and unrepresented, otherwise Warm.

## Missing Information
- Blocking:
  - Current agent relationship.
  - Current property status from approved source.
  - Financing or pre-approval status if a showing is requested.
- Helpful:
  - Preferred showing windows.
  - Main criteria beyond this property.
- Can wait:
  - Full buyer consult details.

## Recommended Next Action
Route property status to `02_property_research/`, then ask `03_client_communication/` for a short reply that does not promise availability until verified.

## Handoff Packet
From: `01_lead_qualifier`
To: `02_property_research`
Matter ID: `MOCK-PORTAL-001`
Stage: Property status and showing triage
Client or lead: Portal buyer lead
Matter: Availability question for 4812 Sample Bend
Urgency: High, weekend showing request
Current status: Lead not yet qualified

## Compliance Flags
- Source reliability: high, listing status is volatile.
- Privacy or sensitive data: low.
- Advertising or broker-review: low, one-to-one reply.

## Human Review
- Reviewer needed: Diana or assigned agent.
- Review reason: property availability and showing guidance.
- Cannot proceed until: status is checked or reply clearly says status is being verified.
```

## Example 3, Referral Text

Input:

```text
Past client texted: "My friend Morgan may sell in the fall. Can I connect you?"
```

Output:

```md
## Lead Summary
Potential seller referral from a past client. Relationship context matters.

## Lead Temperature
Warm

## Missing Information
- Blocking:
  - Permission for introduction.
- Helpful:
  - Property address.
  - Desired sale timing.
  - What Morgan wants help with: pricing, prep, timing, or process.
- Can wait:
  - Condition details and motivation.

## Recommended Next Action
Ask for permission to be introduced and keep the first message warm, not salesy.

## Suggested Follow-Up
"Absolutely, happy to help. If Morgan is comfortable, feel free to connect us by text or email and I can start with a simple conversation about timing and prep."
```

## Example 4, Open House Follow-Up

Input:

```text
Open house note: "Taylor came through with partner. Liked the backyard, worried about traffic. No lender yet. Wants to stay under 650k."
```

Output:

```md
## Lead Summary
Buyer lead from open house. Budget and one concern known. Financing not started.

## Lead Temperature
Warm

## Missing Information
- Blocking:
  - Current agent relationship.
  - Permission to follow up by text or email if not already captured.
- Helpful:
  - Timeline.
  - Lender/pre-approval plan.
  - Must-haves beyond yard and budget.
- Can wait:
  - Specific neighborhood preferences.

## Recommended Next Action
Send a short follow-up that references the backyard and traffic concern, then asks whether they want help comparing options under 650k.
```

## Example 5, Seller Inquiry

Input:

```text
Email: "We may sell our house in South Austin this fall. Curious what we should do before listing."
```

Output:

```md
## Lead Summary
Potential seller planning for fall. Needs listing prep guidance and likely property research.

## Lead Temperature
Warm

## Missing Information
- Blocking:
  - Property address.
  - Decision-maker status.
- Helpful:
  - Desired sale month.
  - Current condition and recent updates.
  - Occupancy status.
- Can wait:
  - Full pricing strategy.

## Recommended Next Action
Ask for the address and offer a prep-focused walkthrough. Route to `02_property_research/` once address is available.
```

## Example 6, Just Browsing

Input:

```text
DM: "Honestly just browsing right now, maybe buying next year."
```

Output:

```md
## Lead Summary
Early-stage buyer. Not ready for active search, but could be nurtured.

## Lead Temperature
Nurture

## Missing Information
- Blocking:
  - Current agent relationship before giving tailored search support.
- Helpful:
  - General price comfort.
  - Desired timeline.
  - What they want to learn first.
- Can wait:
  - Detailed criteria.

## Recommended Next Action
Send a no-pressure reply that offers a simple planning conversation or market orientation.

## Suggested Follow-Up
"Totally fine. If next year is the target, the useful thing now is getting oriented so you are not rushed later. I can help you understand budget, timing, and what to watch without turning it into an active search yet."
```

## Example 7, Already Represented

Input:

```text
Lead says: "We have an agent but wanted your take on this house."
```

Output:

```md
## Lead Summary
Lead is already represented. Do not provide property advice or interfere with the agency relationship.

## Lead Temperature
Unqualified unless representation ends or their agent consents.

## Recommended Next Action
Send a respectful boundary reply.

## Suggested Follow-Up
"Thanks for reaching out. Since you are already working with an agent, the right move is to ask them for guidance on that property. If your situation changes in the future, I would be happy to talk then."

## Compliance Flags
- Agency relationship: high, do not advise on the property.
- Advertising or broker-review: low.
- Privacy or sensitive data: low.
```
