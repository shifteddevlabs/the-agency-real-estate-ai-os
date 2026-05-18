# Scenarios

End-to-end demonstrations of how a request moves through The Agency. Each scenario shows the routing decision, every handoff packet along the way, and the final output. Use these as proof the handoff contracts hold across diverse cases, and as reference for what "good" looks like.

All client names, addresses, and details are synthetic.

## Index

| # | Scenario | Flow | Demonstrates |
|---|---|---|---|
| 01 | [New buyer lead + property question](01-buyer-new-lead-property.md) | 00 → 01 → 02 → 03 | Standard intake, source-backed research, voice-aware draft |
| 02 | [Seller listing prep](02-seller-listing-prep.md) | 00 → 01 → 02 → 03 | Seller-side intake, listing agreement gate, comp research |
| 03 | [Returning client](03-returning-client.md) | 00 → 01 (returning mode) → 03 | Lighter intake, relationship awareness, welcome-back tone |
| 04 | [Inspection crisis mid-option](04-inspection-crisis.md) | 00 → 04 → 03 | Renegotiation playbook, time-sensitive decision support |
| 05 | [Wire fraud attempt](05-wire-fraud-attempt.md) | 00 (high risk) → escalate → 03 | Compliance filter catches threat, system refuses to relay |
| 06 | [Broken handoff (rejection)](06-broken-handoff.md) | 02 → 03 (rejected) → 00 | Receiver enforces required fields, protocol is real |

## How To Read A Scenario

Each scenario follows the same shape:

1. **Raw Request** — what the team member types in.
2. **Routing Decision** — orchestrator's choice and why.
3. **Handoff Chain** — every packet, in order, with all fields populated.
4. **Final Output** — what reaches the team member or client.
5. **What This Demonstrates** — which architecture principles this scenario exercises.

The handoff packets in these scenarios are reference examples. Real packets may include fewer fields (use the minimum schema in `../handoff-contracts.md`) or more (for compliance-sensitive handoffs).
