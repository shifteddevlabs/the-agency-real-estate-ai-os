# Assistant vs. Agent Roles

The Agency is used by both licensed real estate agents (Diana) and unlicensed support staff (assistants, transaction coordinators, intern). The system's specialist folders are written for the agent's perspective, but most actual typing into the system is done by support staff.

This reference enumerates what each role can do, what must route to Diana, and where the role boundary actually lies.

## Why This Matters

Real estate is a licensed activity. Unlicensed support staff cannot:

- Negotiate price, terms, or contract language with another party.
- Show property to a buyer.
- Make representations about value, condition, or suitability.
- Sign or accept contracts on behalf of a client.
- Independently advise a client on offer strategy, financing, or negotiation.

What they CAN do is everything that's clerical, organizational, or draft-preparation. That's where The Agency fits.

This isn't just legal compliance. It also protects Diana's relationship with the client and protects the assistant from saying something that creates exposure.

## Role Matrix

### Diana (licensed agent)

**Can do (must do):**

- Review and send every client-facing message.
- Negotiate offer terms with the other side.
- Show property to qualified buyers (with signed rep agreement on file).
- Advise the client on price, strategy, contract terms, and tradeoffs.
- Sign listing agreements, buyer rep agreements, and amendments on her own behalf.
- Make final decisions on what gets escalated to broker, attorney, or other specialists.

**Cannot delegate:**

- Showing property.
- Negotiation with the other side.
- Strategic advice to the client.
- Signing on the client's behalf (only the client can do that, in most cases).
- Final sign-off on any client-facing communication.

### Support staff / assistant (unlicensed)

**Can do:**

- Drag the folder into a Claude/ChatGPT/Gemini project. Set up onboarding.
- Type lead notes, property questions, client updates, transaction notes into the system.
- Read the orchestrator's routing decisions and the specialists' outputs.
- Review drafts the system produces. Flag voice issues, factual gaps, or compliance concerns to Diana.
- Run the test suite (if any), check whether drafts hit voice-score thresholds.
- Capture handoff packets and store them in the deal file.
- Coordinate logistics: schedule inspections, schedule walkthroughs, coordinate with title, set calendar invites.
- Update the deal file with new information as it comes in.
- Phone-verify wire instructions with title (this is logistics, not advice).
- Reply to non-substantive logistics emails on Diana's behalf if she has explicitly authorized this for that specific deal ("Diana asked me to confirm the inspection time on her behalf").

**Cannot do:**

- Negotiate price, terms, repairs, credits, or any contract content.
- Schedule a showing for a buyer (Diana does this; the rep agreement requirement applies).
- Tell a buyer or seller what a property is worth.
- Tell a buyer or seller what offer to make.
- Sign or accept contracts on a client's behalf.
- Discuss repairs, severity, cost, or strategy with the client.
- Send a client-facing message that Diana hasn't reviewed (with the narrow logistics exception above).
- Independently respond to compliance-sensitive questions (fair housing, advertising, agency, advice).

**Must always do:**

- Hand off to Diana any client-facing draft that is not pure logistics.
- Surface any compliance flag from the orchestrator to Diana.
- Phone-verify wire instructions with title before any wire is sent. The system never relays them and neither do you.

## How The Agency Reflects This

The system's outputs are labeled with `Needs Diana review` or `Client-ready draft` (which still means "ready for human review"). The assistant's job is to:

1. Type the request.
2. Read what the system produced.
3. Identify anything that needs a human's eye.
4. Route it to Diana for review.
5. Once Diana approves, send (or hand to Diana to send).

You are NOT trying to make the system produce a final-form output that you then send directly. That defeats the architecture.

## Specific Situations

### A new lead just came in

- **You:** Type the lead into the chat. Read the lead summary and the suggested questions.
- **You:** If the lead is missing critical info (contact method, budget, timeline), surface that.
- **You:** Hand the draft replies to Diana for review.
- **Diana:** Reviews, sends the first reply (or asks you to send a logistics-only reply on her behalf).

### A buyer wants to tour a home

- **You:** Capture the request. The system will flag that a signed buyer rep agreement is required before any tour.
- **You:** If no rep agreement, the next step is a buyer consult, schedule that.
- **Diana:** Conducts the rep agreement consult, signs the agreement, then schedules the tour.
- **You:** Add the rep agreement to the deal file. Coordinate the tour calendar.

### An inspection report comes in

- **You:** Capture the report in the system. Read the structured options the transaction coordinator produces.
- **You:** Set up the specialist evaluations (structural, HVAC, etc.) per the playbook.
- **You:** Add the report and specialist findings to the deal file.
- **Diana:** Discusses the report and options with the client. Diana decides path with the client.
- **You:** Once Diana decides, you draft the amendment via the system, hand to Diana for sign-off.
- **Diana:** Signs the amendment, delivers it to the other side.

### Wire fraud attempt

- **You:** Do NOT relay wire instructions. Do NOT respond to the email with anything substantive.
- **You:** Call the title officer directly using a phone number from a prior verified email.
- **You:** Notify Diana immediately.
- **Diana:** Decides whether to escalate to broker and IC3. Drafts the client phone-call script via the system.
- **You:** Help coordinate the client call. Save evidence of the fraud attempt.

### Client asks something compliance-sensitive

(e.g., "Is this neighborhood safe?" or "Should I waive inspection?")

- **You:** Do NOT answer directly. Capture the question in the system; the orchestrator will refuse and produce a compliant rephrase.
- **You:** Hand the rephrase + the client's original question to Diana for review.
- **Diana:** Decides the right response. May call the client rather than text.

## When You're Unsure

If you can't tell whether something is logistics or substantive, treat it as substantive and route to Diana. The cost of one extra hand-off is small. The cost of crossing the line on agency, negotiation, or advice can be a license issue, a regulator complaint, or a deal loss.

A useful test: "Could a court or regulator argue that what I'm about to say is real estate advice or negotiation?" If yes or maybe, route to Diana. If no, you can probably handle it.

## What This Reference Does NOT Cover

- Specific state licensing rules. Texas TREC has its own definitions of what unlicensed activity is. Treat this document as a working baseline, not a legal rulebook. Diana's broker is the official answer for how the brokerage interprets those rules.
- New construction, commercial, or specialty transactions. Those have their own boundaries.
- The agent's own internal training and standards for what they delegate. Diana may be more conservative or more permissive than this baseline; she decides.

When in doubt, ask Diana.
