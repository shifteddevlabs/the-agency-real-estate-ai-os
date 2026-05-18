# The Agency

A plain-English AI playbook for Diana's small Austin real estate team.

The Agency is not software. It is a folder you add to Claude, ChatGPT, or Gemini so the AI knows how Diana's team wants to handle leads, property questions, client messages, and active deals.

You type the messy real-world request. The Agency turns it into the next safe step, a draft, or a handoff note for the right part of the team.

## Start Here

If this folder is already loaded into your AI project:

1. Open the Agency project.
2. Start a new chat.
3. Paste the lead, client note, property question, draft request, or deal update.

Use this starter prompt:

```text
Use The Agency. Help me with this:

[paste the lead, client note, property question, or deal update]
```

The AI should tell you what it knows, what is missing, what is risky, and what to do next.

You do not need to open the folders during normal use. The folders are there so the AI has rules to follow.

## 5-Minute Setup

Do this once before using The Agency with a real team.

1. Open Claude, ChatGPT, or Gemini.
2. Create a new project, GPT, or Gem.
3. Add this entire folder to the project files. If you are not sure how, ask the AI app: `How do I add a folder of files to this project?`
4. Start a new chat.
5. Type: `start onboarding`
6. Answer the setup questions one at a time.
7. When the AI creates `profile.md`, ask it to save the file in `_user_data/` if it has file access. If it cannot save files, ask it for the exact text to paste into that file.

After that, open the project and type what you need.

For the team setup questions, use [support/setup/team-onboarding.md](support/setup/team-onboarding.md). For Diana's writing style, use [support/setup/voice-onboarding.md](support/setup/voice-onboarding.md).

## First Lead Example

You type:

> Got a buyer text from Mike: "My friend Alex is moving to Austin in October, looking under $750K, East Austin, pre-approved. Please reach out."

The Agency should return:

- A short lead summary.
- The missing pieces, like Alex's contact info and buyer agreement status.
- Any safety flags, like do not suggest a showing until the written buyer agreement status is confirmed.
- A reply to Mike.
- A draft first message to Alex, held for human review.

Then you review the drafts, send from your own email or phone, and ask:

```text
Create or update the lead/deal log for this lead. If you can save files, save it in `lead-deal-logs/`. If not, give me the exact text and filename to use, plus a CRM notes version.
```

That is the loop: paste the real note, get the next safe step, review it, then save the lead/deal log if you need to pick up later.

## What You Can Ask

- "I have a new lead, can you help me qualify them?"
- "Tell me what we can safely say about 1234 Main St."
- "Draft a follow-up email to a buyer who has not responded."
- "We have an accepted offer, what do we need to track?"
- "This client question feels risky, what is the safest reply?"

If the AI gets stuck, use:

```text
I'm stuck. What's the cleanest next step?
```

If the draft sounds wrong, use:

```text
The voice is off. Make it warmer, shorter, and more like Diana.
```

## How The Team Works

Every request starts at `00_orchestrator/`. Think of it as the front desk. It decides who should handle the request and flags anything risky before the work moves forward.

| Folder | Plain-English role | Use it for |
|---|---|---|
| `00_orchestrator/` | Front desk | Routes every request and flags risk |
| `01_lead_qualifier/` | Lead intake | New buyers, sellers, referrals, returning clients |
| `02_property_research/` | Property notes | Address, area, listing, and research questions |
| `03_client_communication/` | Draft writer | Emails, texts, follow-ups, scripts |
| `04_transaction_coordinator/` | Deal tracker | Accepted offers, deadlines, closing tasks |

The folder names are for the AI and for reviewers. Day to day, the team can just type the request in normal language.

## Typical Flow

1. A team member pastes a real lead, client note, property question, or deal update.
2. The front desk decides who should handle it and flags anything risky.
3. The right specialist creates the next step, draft, checklist, research note, or handoff note.
4. A human reviews before anything goes to a client or official deal file.
5. If the work needs to continue later, the AI creates or updates the lead/deal log.

## Handoff Notes

When one folder passes work to another, it creates a handoff note. A good handoff note says:

- Who is handling the next step.
- What is already known.
- What is missing.
- What needs human review.
- What should not happen yet.

Most users never fill this out by hand. Ask the AI to create or check the handoff note.

For the formal handoff rules, see [support/reference/handoff-contracts.md](support/reference/handoff-contracts.md).

## Keep Track Between Chats

AI chats do not reliably remember old work. For any active lead or deal, keep a short lead/deal log.

Ask the AI to save it in your private `lead-deal-logs/` folder. If the AI app cannot write files, ask it for the exact filename and text, then paste that into your CRM notes or deal file.

Use [support/reference/lead-deal-log-template.md](support/reference/lead-deal-log-template.md) when you need a clean starting point.

Your CRM, transaction platform, or brokerage system is still the official record. The lead/deal log is just a memory aid for the AI.

## Safety Rules

The Agency drafts and organizes. A human still reviews and sends.

- Do not send client-facing drafts without review.
- Do not paste real client private details into a public repo.
- Do not include wire instructions in AI output.
- Confirm written buyer agreement status before suggesting a showing.
- Use objective facts for neighborhood questions, not steering language.
- Do not let the AI give legal, tax, lending, inspection, appraisal, or valuation advice.
- Recheck property facts and deadlines before relying on them.

If something looks unsafe, stop and ask Diana, the broker, title, lender, attorney, inspector, or another qualified professional.

## Onboard A New Team Member

1. Read this README.
2. Try the first lead example above.
3. Read [support/setup/team-onboarding.md](support/setup/team-onboarding.md).
4. Read [support/setup/voice-onboarding.md](support/setup/voice-onboarding.md).
5. Practice with one scenario from [support/reference/scenarios/](support/reference/scenarios/).

A new team member is ready when they can paste a lead, understand the next step, and know when a human needs to review before sending.

## For Reviewers

The assignment asks whether the architecture makes sense, whether handoffs are real, whether the README can onboard a stranger, and whether the design decisions are intentional.

This project is built from the JJ AI Studio point of view: AI systems should feel useful before they feel impressive. The structure comes from two practical choices. First, a nontechnical realtor can use the README and normal language, while a tech-savvy realtor can inspect and tune the folders. Second, every request starts at the front desk before a specialist writes anything. That makes risk visible early, especially fair housing, advertising, source reliability, deadlines, wire fraud, and buyer agreement status.

What I built:

- Five required specialist folders.
- A root README that a new user can follow.
- Clear handoff rules between folders.
- Voice setup for Diana's team.
- Safety rules for client-facing work.
- Mock scenarios for testing the flow without real client data.

The required structure is complete: each specialist folder has `identity.md`, `rules.md`, `examples.md`, and `handoff.md`. The only extra root folders are `_user_data/`, `lead-deal-logs/`, and `support/`. `_user_data/` and `lead-deal-logs/` are part of real team use. `support/` keeps setup, reference, and testing material out of the main path.

If I had another week, I would record a short Loom walkthrough for each major LLM so anyone can load and use the folder, then add Austin-specific source packs, more transaction checklist examples, a Spanish-language human-review path, and a scored mock test report.

For the deeper read:

- [support/reference/design-notes.md](support/reference/design-notes.md), why the structure works.
- [support/reference/handoff-contracts.md](support/reference/handoff-contracts.md), formal handoff rules.
- [support/reference/failure-modes.md](support/reference/failure-modes.md), what can go wrong and how to recover.
- [support/reference/packet-validation-checklist.md](support/reference/packet-validation-checklist.md), quick check before relying on a handoff.
- [support/reference/submission-writeup.md](support/reference/submission-writeup.md), 100-word submission note.

## Manual Prompts

Use these only if the AI project does not automatically read the folder.

### Route A Request

```text
Use The Agency. Start with 00_orchestrator.

Route this request, flag risks, and tell me the next safe step:

[paste lead note, client message, property question, or deal update]
```

### Qualify A Lead

```text
Use The Agency. Start with 01_lead_qualifier.

Qualify this lead. Give me a short summary, missing information, safety flags, and the next client-safe draft if one is safe:

[paste lead note]
```

### Track A Deal

```text
Use The Agency. Start with 04_transaction_coordinator.

Review this deal update. Tell me verified deadlines, missing proof, risk flags, and what the client can safely be told:

[paste deal update]
```
