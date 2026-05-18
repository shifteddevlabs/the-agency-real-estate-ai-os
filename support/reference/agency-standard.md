# Agency Standard

The Agency Standard is the quality bar every specialist uses before work moves forward.

It is not another specialist. It is the shared checklist that keeps Diana's judgment, voice, safety rules, and source discipline visible across the whole process.

## Use This Standard When

- A handoff packet is created or received.
- A client-facing draft is produced.
- Property or market research becomes a recommendation.
- A deadline or transaction task is added to a log.
- A matter appears in the Deal Desk.
- A specialist refuses, returns, or escalates work.

## The Standard

Before output moves forward, it must be:

| Standard | Meaning |
|---|---|
| Safe | It does not create fair-housing, wire-fraud, privacy, representation, advertising, legal, tax, lending, appraisal, inspection, or valuation risk. |
| Sourced | Material facts name the source, date checked, and limits. |
| Specific | The output names the client or matter, stage, current state, missing information, and next owner. |
| Useful | The next step is clear enough for a busy real estate team member to act on. |
| Human-reviewed | Anything client-facing, deadline-related, or compliance-sensitive has a named human review gate. |
| Voice-fit | Client drafts sound like the selected human voice or neutral team voice, not generic AI copy. |
| Traceable | The Matter ID, trail, latest handoff, and log update path are clear. |

## Quick Check Prompt

```text
Use The Agency Standard.

Check this output before it moves forward. Return pass/fail, what fails, and the safest next step.

[paste output]
```

## Pass/Fail Output

```md
## Agency Standard Check

Pass or fail:

## Fails Because

-

## Fix Before Proceeding

-

## Safest Next Step

-
```

## Specialist Responsibilities

### 01 Lead Qualifier

The lead qualifier owns:

- Lead type.
- Lead temperature.
- Current agent or representation status.
- Buyer-representation or listing-agreement gate.
- Next follow-up question.
- Whether the lead can safely move to research, communication, or transaction coordination.

The lead qualifier must not move a buyer toward a showing until buyer-representation status is confirmed.

### 02 Property Research

Property research owns:

- Source quality.
- Source checked date.
- What each source can and cannot prove.
- Confidence level.
- Client-shareable versus internal-only labels.
- Objective, non-steering framing.

Property research must not convert weak or stale source material into client-ready advice.

### 03 Client Communication

Client communication owns:

- Draft status.
- Channel.
- Voice fit.
- Voice score.
- Human review notes.
- Broker-review, source-review, language-review, and Diana-review flags.

Client communication must not claim a message was sent. It drafts only.

### 04 Transaction Coordinator

Transaction coordination owns:

- Verified dates.
- Unverified dates.
- Checklist owner.
- Proof needed.
- Escalation owner.
- Deadline and wire-fraud gates.

Transaction coordination must not treat memory, chat notes, or guesses as verified contract facts.

## Risk Slip Legend

Use this short label when the risk needs to be easy to scan.

| Slip | Meaning | Action |
|---|---|---|
| `RED` | Stop. High-risk compliance, money, legal, deadline, wire, or representation issue. | Escalate to Diana, broker, title, lender, attorney, inspector, or another qualified owner. |
| `YELLOW` | Proceed only after human review. | Draft or prepare, but do not send or rely yet. |
| `BLUE` | Source, proof, or context missing. | Gather or verify before using. |
| `GREEN` | Routine, low-risk work. | Continue with normal human review gates. |

## Minimum Footer

For any output that moves work forward, include:

```md
Agency Standard:
- Risk slip:
- Human review:
- Next owner:
- Log update needed:
```
