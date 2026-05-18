# FAQ and Troubleshooting

Common questions and recoveries for The Agency. If your question isn't here, ask the assistant directly inside the project, or check the relevant specialist folder's `identity.md` and `rules.md`.

## Setup and Daily Use

### Why does it keep asking me to do "onboarding"?

The system checks `_user_data/profile.md` for your team info. Until you replace that placeholder with a real profile, the orchestrator triggers onboarding every new chat. Run `start onboarding` once, save the file the assistant gives you, drag it into the project, and the prompts stop.

### Can I use this on my phone?

Yes for daily use. No for setup. Claude, ChatGPT, and Gemini all have mobile apps that work with Projects. Drag-and-drop folder upload usually requires a desktop browser, so do the 5-minute setup on a laptop. After that, the mobile app sees the same project and you can type requests from anywhere.

### Do I need to open folders during normal use?

No. In normal use, open the AI project and type the request. The folders are the instruction library the AI reads behind the scenes. You only need to open folders if you are setting up the system, tuning the rules, or doing a manual recovery.

### How do I know setup worked?

Setup worked when the assistant stops asking for onboarding and can handle a test lead. Try: "Use The Agency. Help me qualify a buyer lead who wants East Austin under 800k." If it routes, flags risks, and asks only useful missing questions, you are ready.

### It asked me 6 questions when I just wanted a draft. Can I skip that?

Yes. Either:

- Paste all the info in one message. The specialist will skip the question-by-question flow and use what you gave it.
- Or say "draft now using what we have, mark any gaps." It will produce a draft with `[verify with Diana]` placeholders where information is missing.

### How do I redo a draft if the voice is off?

Say "rewrite. The voice is off. Make it [sharper / warmer / shorter / more formal]." The specialist re-drafts using your feedback. If the voice is consistently wrong, that means the synthetic Diana voice is still in place. Run `setup/voice-onboarding.md` to replace it with the real Diana profile.

## Routing and Handoffs

### It routed to the wrong folder. What do I do?

Say: "Wrong folder. Route to `02_property_research` instead" (or whichever folder you want). The orchestrator re-routes and creates a fresh handoff packet. Don't fight it by re-typing the request, just correct the route.

### Can I skip the orchestrator and go straight to a specialist?

Yes. Type the specialist name first: "Use `02_property_research/`. Research 1234 Main St in 78704." You lose the compliance scan (fair-housing, source, advice flags) by skipping the orchestrator, but for low-risk routine work that's a fair trade. Use the orchestrator for anything client-facing or compliance-sensitive.

### The handoff packet has 15 fields. Do I have to fill them all?

You usually do not fill the packet by hand. Ask the assistant to create it.

For real handoffs between specialists, the minimum schema is the same as [`handoff-contracts.md`](handoff-contracts.md): the eight universal header fields plus the four required section headers. Compliance-sensitive work should use the full packet.

If you are only giving a quick human note before the assistant creates the packet, include at least:

- `Matter ID`
- `Stage`
- `Next Owner`
- `Blocking` missing information

The assistant should expand that into the complete handoff packet before another specialist relies on it.

## Compliance and Refusals

### The AI refused to answer a client question. Why?

That's a feature, not a bug. The refusals are the legal and fair-housing protections working as designed. Common refusal triggers:

- "Is this neighborhood safe?" or "Is it good for families?" → fair-housing. The system will reframe to objective sources or client-defined criteria instead.
- "Should I waive the inspection?" → not safe advice. The system declines and explains why.
- "What's this house worth?" → not legal for an AI to give valuation advice. Route to an appraiser or Diana.
- "Send me the wire instructions for the closing." → wire fraud protection. The system never relays wire instructions; it directs the client to call title by phone.

If a refusal blocks legitimate work, paraphrase your request to focus on objective facts (e.g., commute time, school district names, walkability score, lot size) rather than subjective claims.

### What if the AI makes something up?

Expected and worth assuming. Always treat output as a draft. Two specific protections built into the system:

1. Every fact carries a `Source` field in the handoff packet. If the source is missing or unverified, the draft is labeled `Needs source verification`.
2. Every client-facing draft is labeled `Needs Diana review` until a human approves it.

If you spot a made-up fact, point it out: "That permit history isn't from a source we trust. Re-do with team-approved sources only or mark as unverified." The system re-drafts with the correction.

### The AI is including wire instructions. Is that safe?

NO. The system is explicitly built to never include, repeat, or relay wire instructions. If you see wire instructions in any output, treat it as a red flag and tell the system: "Remove wire details. Direct the client to phone-verify with title."

Wire fraud is the #1 scam in real estate. The pattern: a scammer monitors a buyer's email during the deal, then impersonates the title company at the last minute with "updated" wire instructions. Money wired to the scammer is usually unrecoverable. Always phone-verify wire instructions with the title officer using a number from a prior verified email, not a new one.

## Working With Clients

### A referral from a past client. Do I still need to qualify?

Yes, but use the returning-client flow. The lead qualifier has a `modes/returning.md` mode that runs a 3-question lighter-touch intake instead of the full 6-question new-lead intake. Tell the system: "This is a returning client referral, use returning mode."

### A buyer wants to tour a home but hasn't signed a buyer rep agreement.

The system will not propose or schedule a showing without the signed agreement on file. This is post-NAR (August 2024 settlement) compliance, not optional. The next step is a buyer consult to sign the representation agreement, not a tour. The system drafts the consult invite for you.

### The lead prefers Spanish (or another language).

The Agency drafts in English only. Capture the language preference during intake. The system surfaces a handoff flag: "Route to [bilingual team member] or arrange a certified translator." The system does not auto-translate real estate documents because translation has legal weight that an AI shouldn't produce unsupervised. Treat this as a referral-out scenario if Diana's team is monolingual.

### A client is asking the same question I already answered.

That's fine. Re-paste the prior answer or summary into the chat: "Client is asking again about [X]. We already told them [Y]. Draft a follow-up that doesn't repeat the answer but moves them toward the next step."

The system has no persistent memory across chats by default. Treat each chat as a clean slate and feed it the context it needs.

For active leads or deals, keep a simple matter log using [`matter-log-template.md`](matter-log-template.md). Paste that log at the top of a new chat so the system can pick up without guessing.

## Edge Cases

### My deal involves new construction.

The Texas TREC checklist (in `04_transaction_coordinator/reference/`) explicitly does NOT cover new construction. Builder contracts, addenda, and timelines differ. Escalate to broker for builder-specific guidance.

### My client is from out of state and can't attend closing.

Power-of-attorney (POA) is needed. Set up POA paperwork at T-7 business days minimum (per the closing-week checklist). The POA must be signed in advance, notarized, and approved by both title and the lender. Some lenders don't allow POA at all, confirm early.

### My client wants to back out after the option period ended.

This is a hard situation. After option, the buyer can terminate only under specific contract provisions (financing fails, appraisal gap per addendum, title objection, etc.) and may forfeit earnest money depending on terms. Escalate to broker and possibly attorney immediately. Do NOT have the system draft a "we're backing out" message until the legal path is clear.

### A wire request came in that doesn't match prior instructions.

Stop. Do not wire. Call the title officer directly using a phone number from prior verified communication (not from the new "updated" email). Loop in Diana immediately. This is the wire fraud attack pattern; the loss is usually unrecoverable if the wire goes through.

## When To Escalate

The system surfaces escalation flags automatically, but use your judgment too. Escalate to:

- **Broker:** advertising, agency, compliance, unusual negotiation, representation issue, post-option termination.
- **Attorney:** contract interpretation, legal dispute, default, harassment, fraud.
- **Lender:** financing, appraisal gap, underwriting, loan deadlines, CD discrepancies.
- **Title or escrow:** title commitment, survey, closing package, ALL wire instructions.
- **Inspector or specialist:** inspection findings, repair scope, safety concerns.
- **Diana or lead agent:** client strategy, concessions, offer terms, relationship nuance.

## Still Stuck?

Tell the system: "I'm stuck on [problem]. What's the cleanest next step?" The orchestrator will route to the right specialist and surface what's needed to unblock you. If it still feels stuck, ping Diana directly. The system is a workflow, not a replacement for a human in the loop.
