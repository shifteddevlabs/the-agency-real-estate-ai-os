# FAQ

Plain-English help for The Agency.

## Setup And Daily Use

### Why does it keep asking for onboarding?

The AI is looking for your team profile in `_user_data/profile.md`. Run `start onboarding` once, then ask the AI to save the profile there if it has file access. If it cannot save files, ask for the exact text to paste into `_user_data/profile.md`, then add that file to the project files.

If you are not sure how to add it, ask the AI app itself:

```text
How do I add this profile file to my project files?
```

### Can I use this on my phone?

Yes for daily work. Do setup on a laptop because uploading the folder is easier there. After setup, you can open the same AI project on your phone and type normal requests.

### Do I need to open the folders?

Usually no. Open the project and type the request. The folders are the rulebook the AI reads in the background.

Open folders only when you are setting up the system, changing rules, or manually fixing a wrong route.

### How do I know setup worked?

Try this:

```text
Use The Agency. Help me qualify a buyer lead who wants East Austin under 800k.
```

Setup worked if the AI gives a short lead summary, flags risks, and asks only useful missing questions.

### It asked too many questions. Can I skip that?

Yes. Say:

```text
Draft now using what we have, and mark any gaps.
```

The AI should draft with clear placeholders where information is missing.

### The draft does not sound like Diana. What do I do?

Say:

```text
Rewrite. Make it warmer, shorter, and more like Diana.
```

If the voice is often wrong, run [../setup/voice-onboarding.md](../setup/voice-onboarding.md) and replace the starter voice with Diana's real examples.

## Routing And Handoffs

### It picked the wrong folder. What do I do?

Tell it the correction:

```text
Wrong route. Send this to property research instead and explain why.
```

You do not need to restart the whole chat.

### Can I skip the front desk and go straight to a folder?

Yes for low-risk work. Example:

```text
Use 02_property_research. Review these listing notes.
```

For anything client-facing, risky, or deadline-related, start with The Agency or `00_orchestrator` so the safety check happens first.

### Do I have to fill out a handoff note by hand?

Usually no. Ask the AI to create it.

If you are writing a quick human note, include:

- the lead or deal name
- the stage
- what is known
- what is missing
- who should handle the next step
- what should not happen yet

The formal handoff rules are in [handoff-contracts.md](handoff-contracts.md).

### Do I have to save lead/deal logs myself?

Only if your AI app cannot write files.

Try this first:

```text
Create or update the lead/deal log. If you can write files, save it in `lead-deal-logs/`. If not, give me the exact filename and text.
```

Your CRM or transaction system is still the official record. The lead/deal log just helps the AI pick up the work later.

## Safety

### The AI refused to answer. Why?

That usually means the safety rules are working. Common triggers:

- neighborhood safety or "good for families" questions
- legal, tax, lending, inspection, appraisal, or valuation advice
- showing requests before buyer agreement status is clear
- wire instructions
- unverified property facts or deadlines

Ask for objective facts instead, like commute time, school district boundaries, lot size, floodplain source, permit history, or next steps to verify.

### What if the AI makes something up?

Treat every answer as a draft. Ask:

```text
What source supports that? If there is no source, mark it unverified.
```

Do not send or save unsupported facts as final.

### The AI included wire instructions. Is that safe?

No. Stop immediately.

Remove the wire details and call title or escrow using a phone number from prior verified communication. Never rely on wire instructions from a new email or AI output.

## Working With Clients

### A referral came from a past client. Do we still qualify them?

Yes, but use a lighter touch. Say:

```text
This is a returning client referral. Use the returning-client flow.
```

### A buyer wants to tour, but buyer agreement status is unclear.

Do not draft a showing invite yet. Confirm the written buyer agreement status first, then decide the next step with Diana or the broker.

### The lead prefers Spanish or another language.

Capture the preference and route to a qualified bilingual team member or translator. The Agency drafts in English only unless the team adds a reviewed language workflow.

### The client is asking the same question again.

Paste the earlier answer and ask for a follow-up:

```text
Client is asking again about [topic]. We already told them [summary]. Draft a short follow-up that moves them to the next step.
```

## Still Stuck?

Say:

```text
I'm stuck on [problem]. What's the cleanest next step?
```

If the answer still feels wrong, ask Diana or the right human reviewer. The Agency is a workflow, not a replacement for judgment.
