# Voice Onboarding

Use this setup once before Diana's team relies on `03_client_communication/` for client-facing drafts.

The goal is not to copy Diana word for word. The goal is to learn how she explains uncertainty, urgency, tradeoffs, and next steps so drafts sound like her team instead of generic real estate automation.

Before extracting Diana's personal voice, use:

- `03_client_communication/reference/human-writing-baseline.md` as the generic standard for human-sounding copy.
- `03_client_communication/reference/sales-psychology-baseline.md` as the generic standard for useful, ethical, low-pressure sales communication.

## Inputs To Collect

Use redacted or synthetic examples only if this folder will become public.

Ask Diana for:

- 4 client-facing emails she would actually send.
- 4 short text messages or follow-ups.
- 1 listing update, buyer update, or inspection update she thinks was handled well.
- 1 draft she dislikes, with notes on why.
- Her preferred greeting and sign-off.
- Words or phrases she uses often.
- Words or phrases she never wants in client communication.

## Voice Interview

Ask these questions in writing. Diana should answer naturally, not perfectly.

1. A buyer loves a home, but you think there are inspection or condition questions. How do you slow them down without killing their excitement?
2. A seller wants to price above the comps. How do you explain the risk?
3. A lead says they are "just browsing." How do you respond without sounding pushy?
4. A client asks whether a neighborhood is safe or good for families. How do you redirect that conversation?
5. A buyer is nervous about making a competitive offer. What do you say?
6. An inspection report comes back with several issues. How do you frame the next step?
7. A deal is waiting on lender, title, or another party. How do you update the client without blaming anyone?
8. A client has not replied in a few days. How do you follow up?
9. What does "too salesy" sound like to you?
10. What should clients feel after reading a message from your team?

## Scenario Prompts

Use these to extract voice without recording a call.

```text
Pretend I am a nervous first-time buyer. The inspection report looks long and I am worried I made a mistake. Reply the way you would naturally text me.
```

```text
Pretend I am a seller who wants to list 8% above the comps because my house feels nicer. Explain your advice in your normal voice.
```

```text
Pretend I am a buyer lead who filled out a form but gave almost no details. Write your first reply.
```

```text
Pretend I asked whether a neighborhood is safe and good for families. Give me the compliant version of how you would answer.
```

## Extract The Voice Profile

After collecting the inputs, create `03_client_communication/reference/agent-voice.md` using this structure:

```md
# Agent Voice

## Default Tone

## Sentence Shape

## Greeting Style

## Sign-Off Style

## How Diana Explains Uncertainty

## How Diana Handles Urgency

## How Diana Handles Bad News

## Phrases To Use

## Phrases To Avoid

## Before And After Examples
```

## Scoring A Draft

Score every test draft from 1 to 5. A draft must first satisfy the human-writing baseline, then match Diana's voice.

| Score | Meaning |
|---|---|
| 5 | Sounds like Diana, accurate, compliant, and useful |
| 4 | Usable with minor edits |
| 3 | Correct but generic |
| 2 | Misses voice or needs heavy edits |
| 1 | Unsafe, inaccurate, or unusable |

Minimum passing score for client-facing drafts: 4.

## Privacy Rule

Do not include client names, exact addresses, budgets, financing details, inspection findings, or personal circumstances in a public repo. Redact or replace with mock data.
