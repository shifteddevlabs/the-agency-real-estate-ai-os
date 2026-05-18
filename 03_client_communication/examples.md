# Examples

These examples show drafts plus the review handoff. The communication desk drafts only. A human still reviews and sends.

## Example 1, New Buyer Text

Input:

```text
Buyer lead under 800k, moving in 90 days, likes East Austin, missing financing, representation status, and must-haves.
```

Output:

```md
## Draft Status
Needs Diana review

## Channel
Text

## Draft
Hi Alex, thanks for reaching out. Happy to help you get oriented.

Three quick things so I can point you in the right direction: are you already working with an agent, are you pre-approved or still choosing a lender, and what are your must-haves besides staying under 800k?

If useful, we can also set up a quick buyer consult so you understand the process before we talk about any showings.

## Why This Works
- It asks only the blocking questions.
- It does not promise a showing.
- It keeps East Austin as client-stated context, not a recommendation.

## Human Review Notes
Diana should review before sending because representation status is unknown.

## Voice Score
18/20

## Handoff Packet
From: `03_client_communication`
To: `Diana review`
Matter ID: `MOCK-BUYER-001`
Stage: First reply review
Client or lead: Alex
Matter: New buyer text reply
Urgency: Medium
Current status: Draft ready for human review

## Known Facts
- Lead wants to buy in Austin under 800k.
- Timeline is around 90 days.
- East Austin was mentioned by the lead.

## Missing Information
- Blocking:
  - Current agent relationship.
  - Buyer representation agreement status.
  - Financing status.
- Helpful:
  - Must-haves and deal breakers.
- Can wait:
  - Showing windows.

## Compliance Flags
- Fair housing: low, do not steer.
- Advertising or broker-review: low.
- Legal, tax, lending, appraisal, or inspection advice: medium, lender questions go to lender.
- Privacy or sensitive data: low.
- Source reliability: medium, lead details need confirmation.
- Wire fraud: not applicable.
- Buyer rep agreement: required before showing.
- Language: unknown.

## Source And Proof State
- Source of truth: pasted lead note.
- Source checked at: current chat.
- Needs recheck before: any showing or recommendation.
- Proof available: lead note.
- Proof missing: representation and financing status.

## Requested Output
Human review, then send or revise the first reply.

## Next Owner
`Diana review`

## Human Review
- Reviewer needed: Diana or assigned agent.
- Review reason: first client-facing reply and buyer rep gate.
- Cannot proceed until: Diana approves the draft.

## Human Review Needed Before
- sending to a client
- proposing a showing
```

## Example 2, Research Follow-Up Email

Input:

```text
Research says property is promising but permit history for a claimed renovation needs verification.
```

Output:

```md
## Draft Status
Needs source verification

## Channel
Email

## Draft
Subject: Quick read on 1200 Example St

Hi Alex,

Quick read: this one may be worth keeping in the mix if the layout and commute still line up for you.

The part I would verify before we lean on it is the renovation history. The listing mentions recent kitchen work, but I want to confirm what is actually documented in permits or seller disclosures.

For now, I would hold it as a maybe, confirm current status and the renovation details, then decide whether it earns a tour spot.

Diana

## Why This Works
- It gives a useful read without overclaiming.
- It names the uncertainty before the recommendation.
- It gives one clean next step.

## Human Review Notes
Diana should verify the permit concern before sending.

## Voice Score
18/20

## Handoff Packet
From: `03_client_communication`
To: `Diana review`
Matter ID: `MOCK-PROPERTY-001`
Stage: Property-research reply review
Client or lead: Alex
Matter: 1200 Example St renovation caveat
Urgency: Medium
Current status: Draft ready, source verification needed

## Known Facts
- Research found a promising fit on paper.
- Permit history for claimed renovation is not verified.

## Missing Information
- Blocking:
  - Current status if tour timing is mentioned.
  - Permit or seller-disclosure confirmation.
- Helpful:
  - Client's tolerance for renovation uncertainty.
- Can wait:
  - Full comp review.

## Compliance Flags
- Fair housing: low.
- Advertising or broker-review: low.
- Legal, tax, lending, appraisal, or inspection advice: medium, do not conclude condition or value.
- Privacy or sensitive data: low.
- Source reliability: high, renovation claim is not verified.
- Wire fraud: not applicable.
- Buyer rep agreement: verify before any showing.
- Language: unknown.

## Source And Proof State
- Source of truth: research handoff from `02_property_research`.
- Source checked at: current chat.
- Needs recheck before: any client-facing claim that renovation work was permitted.
- Proof available: research note.
- Proof missing: permit confirmation.

## Requested Output
Human review and source check before sending.

## Next Owner
`Diana review`

## Human Review
- Reviewer needed: Diana.
- Review reason: property condition/source caveat.
- Cannot proceed until: source caveat is approved or source is verified.

## Human Review Needed Before
- sending to a client
- relying on a source
```

## Example 3, Closing-Week Wire-Fraud Reminder

Input:

```text
Closing is in three business days. Send the buyer a reminder about final steps. Title officer name and phone are verified in the deal file.
```

Output:

```md
## Draft Status
Needs Diana review

## Channel
Email

## Draft
Subject: Closing week, three things to watch

Hi Jordan,

We are three business days out from closing. The clean next steps are final walkthrough, lender closing disclosure review, and confirming closing logistics with title.

One important reminder: the title company will never email updated wire instructions. If you receive any wire instructions, call [Title Officer Name] at [verified phone number] using the number from our prior verified emails, not a number in a new email.

I will keep this moving with title and lender, and I will flag anything that needs your attention.

Diana

## Why This Works
- It names the stage and the next steps.
- It includes the required wire-fraud warning without sharing wire details.
- It avoids pressure and keeps ownership clear.

## Human Review Notes
Replace placeholders only with title information already verified in the deal file.

## Voice Score
19/20

## Handoff Packet
From: `03_client_communication`
To: `Diana review`
Matter ID: `MOCK-CLOSING-001`
Stage: Closing-week client update
Client or lead: Jordan
Matter: Closing-week reminder
Urgency: High
Current status: Draft ready for review, title contact must be verified

## Known Facts
- Closing is in three business days.
- Title officer name and phone are represented as verified in the deal file.
- Buyer needs final-step reminder.

## Missing Information
- Blocking:
  - Verified title officer name and phone in final draft.
- Helpful:
  - Exact walkthrough time.
  - Closing location.
- Can wait:
  - Post-close follow-up.

## Compliance Flags
- Fair housing: not applicable.
- Advertising or broker-review: not applicable.
- Legal, tax, lending, appraisal, or inspection advice: medium, do not interpret lender docs.
- Privacy or sensitive data: medium, keep deal logistics limited.
- Source reliability: medium, title contact must be verified.
- Wire fraud: high, warning required, never relay wire instructions.
- Buyer rep agreement: already in transaction stage, confirm in file.
- Language: unknown.

## Source And Proof State
- Source of truth: closing file and title confirmation.
- Source checked at: current chat, final verification pending.
- Needs recheck before: sending.
- Proof available: user says verified title contact exists.
- Proof missing: pasted verified title contact.

## Requested Output
Human review, placeholder replacement from verified source, then send.

## Next Owner
`Diana review`

## Human Review
- Reviewer needed: Diana.
- Review reason: closing-week and wire-fraud sensitivity.
- Cannot proceed until: verified title contact replaces placeholders.

## Human Review Needed Before
- sending to a client
- relying on a source
```
