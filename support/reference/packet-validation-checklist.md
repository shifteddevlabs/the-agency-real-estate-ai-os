# Packet Validation Checklist

Run this before a specialist relies on a handoff packet, before a client-facing draft is reviewed, before a deal deadline is added to a live file, or before a lead/deal log is used in a Deal Desk brief.

Ask the assistant:

```text
Check this before I rely on it.
```

For a fuller review, ask:

```text
Use The Agency packet validation checklist.

Review this packet for completeness, risk, and source state. Do not continue the work yet. Return only pass/fail, what is missing, and the safest next step.

[paste packet]
```

The assistant should offer this check automatically before a client-facing draft is treated as send-ready, before a deadline is added to a live deal file, before a Deal Desk brief is trusted, or after a broken handoff.

## Pass Criteria

- `From` and `To` are present.
- `Matter ID` is present and traceable.
- `Stage` matches the actual work state.
- `Client or lead` is named or safely redacted.
- `Matter` is clear in one sentence.
- `Urgency` is set.
- `Current status` says what has already happened.
- `Return to`, `Confidence`, `Trail`, `Stall trigger`, `Next check`, and `Last touched by` are present for full packets.
- Blocking missing information is separated from helpful or later information.
- Compliance flags are filled, not left as placeholders.
- Source of truth is named for every factual claim.
- Source checked timestamp is present for property, market, deadline, or transaction facts.
- Next owner is named.
- Human review owner is named.
- The packet says what cannot happen yet.
- Agency Standard footer is filled with risk slip, human review, next owner, and log update need.

## Automatic Fail Conditions

- Wire instructions, account numbers, or routing numbers appear anywhere in the packet.
- The packet implies a buyer showing before buyer-representation status is known.
- A property status, deadline, price claim, permit claim, or comp claim has no source.
- A client-facing draft is labeled ready to send without Diana or assigned human review.
- The packet contains protected-class assumptions or neighborhood steering language.
- A transaction deadline is based on memory instead of the executed contract or verified deal file.
- A Deal Desk item has no next owner or next check date.
- The risk slip is missing on compliance-sensitive, source-sensitive, or deadline-sensitive work.

## Output Format

```md
## Validation Result

Pass or fail:

## Missing Or Unsafe

-

## Fix Before Proceeding

-

## Safest Next Step

-

## Agency Standard

- Risk slip:
- Human review:
- Next owner:
- Log update needed:
```
