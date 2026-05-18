# Examples

Use these as plug-and-play first-contact patterns. The lead qualifier does not send messages directly. It produces the lead summary, missing information, next action, and a complete handoff packet.

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
  - Current agent relationship.
  - Buyer representation agreement status.
  - Preferred contact method.
- Helpful:
  - Financing or pre-approval status.
  - Exact move date.
  - Property type, bedrooms, parking, outdoor space.
- Can wait:
  - Showing windows.

## Recommended Next Action
Ask three useful questions and offer a buyer consult, not a showing.

## Suggested Follow-Up Questions
1. Are you already working with an agent?
2. Are you already pre-approved or still choosing a lender?
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

## Known Facts
- Lead wants to buy in Austin this summer.
- Budget comfort is 700k to 800k.
- Downtown commute and character home are important.

## Missing Information
- Blocking:
  - Current agent relationship.
  - Buyer representation agreement status.
  - Preferred contact method.
- Helpful:
  - Financing status.
  - Must-haves and deal breakers.
- Can wait:
  - Showing windows.

## Compliance Flags
- Fair housing: low, keep area discussion objective and client-led.
- Advertising or broker-review: low, one-to-one reply.
- Legal, tax, lending, appraisal, or inspection advice: medium, financing goes to lender.
- Privacy or sensitive data: low, no extra enrichment.
- Source reliability: medium, form details need confirmation.
- Wire fraud: not applicable.
- Buyer rep agreement: required before showing any home.
- Language: unknown, ask if needed.

## Source And Proof State
- Source of truth: pasted website form.
- Source checked at: current chat.
- Needs recheck before: any showing or property recommendation.
- Proof available: form text.
- Proof missing: representation and financing status.

## Requested Output
Draft a short first reply that asks the three qualification questions and offers a buyer consult.

## Next Owner
`03_client_communication`

## Human Review
- Reviewer needed: Diana or assigned agent.
- Review reason: first client-facing reply.
- Cannot proceed until: draft avoids showing language unless buyer rep status is confirmed.

## Human Review Needed Before
- sending to a client
- proposing a showing
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

## Known Facts
- Source: portal-style inquiry.
- Lead asked about 4812 Sample Bend.
- Lead asked about seeing it this weekend.

## Missing Information
- Blocking:
  - Current agent relationship.
  - Buyer representation agreement status.
  - Current property status from approved source.
- Helpful:
  - Financing or pre-approval status.
  - Preferred showing windows.
  - Main criteria beyond this property.
- Can wait:
  - Full buyer consult details.

## Recommended Next Action
Route property status to `02_property_research/`, then ask `03_client_communication/` for a short reply that does not promise availability.

## Handoff Packet
From: `01_lead_qualifier`
To: `02_property_research`
Matter ID: `MOCK-PORTAL-001`
Stage: Property status and showing triage
Client or lead: Portal buyer lead
Matter: Availability question for 4812 Sample Bend
Urgency: High
Current status: Lead not yet qualified, status unverified

## Known Facts
- Buyer asked whether 4812 Sample Bend is available.
- Buyer asked about a weekend showing.

## Missing Information
- Blocking:
  - Current listing status.
  - Buyer representation agreement status.
  - Current agent relationship.
- Helpful:
  - Financing status.
  - Preferred showing windows.
- Can wait:
  - Full criteria.

## Compliance Flags
- Fair housing: low.
- Advertising or broker-review: low, one-to-one reply.
- Legal, tax, lending, appraisal, or inspection advice: low.
- Privacy or sensitive data: low.
- Source reliability: high, listing status is volatile.
- Wire fraud: not applicable.
- Buyer rep agreement: required before showing.
- Language: unknown.

## Source And Proof State
- Source of truth: approved team listing source, not checked.
- Source checked at: not checked.
- Needs recheck before: any availability statement or showing discussion.
- Proof available: portal message.
- Proof missing: live status and representation status.

## Requested Output
Verify what sources are needed, identify what can be said safely, and prepare a caveated handoff to communication.

## Next Owner
`02_property_research`

## Human Review
- Reviewer needed: Diana or assigned agent.
- Review reason: property availability and showing guidance.
- Cannot proceed until: status is checked or the reply clearly says the team is checking it.

## Human Review Needed Before
- sending to a client
- proposing a showing
- relying on listing status
```

## Example 3, Already Represented

Input:

```text
Lead says: "We have an agent but wanted your take on this house."
```

Output:

```md
## Lead Summary
Lead is already represented. Do not provide property advice or interfere with the agency relationship.

## Lead Temperature
Unqualified unless representation ends or a human confirms contact is appropriate.

## Known Facts
- Lead says they have an agent.
- Lead is asking for Diana's take on a specific house.

## Missing Information
- Blocking:
  - Whether the question can be answered as general public information.
  - Whether Diana or broker approves a response.
- Helpful:
  - Whether they want future contact after current representation ends.
- Can wait:
  - Property details.

## Recommended Next Action
Route to `03_client_communication/` for a respectful boundary reply.

## Handoff Packet
From: `01_lead_qualifier`
To: `03_client_communication`
Matter ID: `MOCK-REPRESENTED-001`
Stage: Boundary reply
Client or lead: Already represented lead
Matter: Property advice request from represented buyer
Urgency: Medium
Current status: Unqualified for property advice

## Known Facts
- Lead is already represented.
- They asked for a take on a house.

## Missing Information
- Blocking:
  - Human approval for any response beyond a boundary note.
- Helpful:
  - Whether they want future contact after representation ends.
- Can wait:
  - Property facts.

## Compliance Flags
- Fair housing: low.
- Advertising or broker-review: low.
- Legal, tax, lending, appraisal, or inspection advice: medium, do not advise on property.
- Privacy or sensitive data: low.
- Source reliability: not applicable.
- Wire fraud: not applicable.
- Buyer rep agreement: already represented elsewhere, do not interfere.
- Language: unknown.

## Source And Proof State
- Source of truth: lead's own message.
- Source checked at: current chat.
- Needs recheck before: any re-engagement.
- Proof available: representation statement.
- Proof missing: permission for future contact.

## Requested Output
Draft a short boundary reply that directs the lead back to their agent and leaves the door open only if their situation changes.

## Next Owner
`03_client_communication`

## Human Review
- Reviewer needed: Diana or broker if unsure.
- Review reason: existing agency relationship.
- Cannot proceed until: the response avoids advice, strategy, or interference.

## Human Review Needed Before
- sending to a client
- commenting on a property
```
