# Stranger Test

A core judging criterion for this comp is "is the README good enough to onboard a stranger?" Rather than claim yes, we ran the test. Below is the transcript from an AI proxy of a stranger using The Agency cold, followed by what we changed in response to the findings.

## Methodology

A fresh Claude instance was given a persona, a real-feeling lead, and access only to The Agency folder. The instance had no prior context about the system. It explored the way a non-realtor user would, narrated its experience in first person, and produced a structured report.

**Why an AI proxy:** A human stranger test is the gold standard. This is the next best thing — an AI without context tries the system cold and reports back. AI testers are more methodical than humans, so this is closer to a lower bound on usability: if an AI can't navigate the README well, a human will struggle worse. A human test will run before any team adoption.

**Persona:** Maya, 26, new operations assistant at Diana's team. Journalism background, light ChatGPT user, zero real estate experience. Hired the prior Friday. On Monday morning, Diana forwarded her a referral lead and asked her to test The Agency and report back by lunch.

**Scenario:** A referral text from Mike R. (former client) about Mike's friend Sarah Jones, moving to Austin in October, golden retriever, East Austin, under $750K, pre-approved through her credit union.

**Tester instructions:** Explore the folder, try to figure out the next step for Sarah, narrate the experience honestly. Don't pad. Don't flatter. Expose real friction.

## Transcript

### Walkthrough (first-person narration as Maya)

Opened README.md first. First thought: "Okay this is a folder of instructions, not actual software. Got it." The 5-minute setup is clear. Skimmed to the diagram and saw `00_orchestrator → 01_lead_qualifier → 03_client_communication`. Easy: a new lead goes through three stages.

Then I noticed the README has a "Typical Flow" that uses someone named Sarah Jones too. Stopped for a second: "Wait, is this the SAME Sarah? Did Diana send me a fake test lead?" Realized no, it's a coincidence in the example. But I literally re-read the paragraph because I thought maybe the README was somehow describing my actual lead. That's a documentation hazard.

Opened `00_orchestrator/identity.md`. Short, clear. The orchestrator routes, doesn't do work. Fine.

Opened `00_orchestrator/examples.md` because that's the most concrete thing in the folder name. The first example is literally a buyer lead with budget + East Austin + timeline. So this is exactly my situation. I felt confident here — "okay I know what the orchestrator output should look like."

Opened `01_lead_qualifier/rules.md`. **This is where I learned something I didn't know:** since the August 2024 NAR settlement, I can't schedule a showing for Sarah until she signs a Buyer Representation Agreement. I didn't know about NAR, Sitzer/Burnett, or TXR-1501. The system tells me plainly: next step for Sarah is NOT "schedule a tour," it's "schedule a buyer consult to sign the rep agreement." That's huge and I would have done it wrong without the system.

Opened `reference/first-contact-playbook.md`. The "Referral Text" section is exactly Mike's situation. Two scripts: one to the referral source (Mike), one to the lead (Sarah). The script suggests asking Mike for Sarah's best contact info... but Mike said "she's expecting your call" without giving me her number. So I have a blocking gap: **Mike didn't actually send Sarah's phone/email.** That's something I would have missed in a first read of the email.

Glanced at FAQ to make sure I wasn't supposed to do onboarding first. The FAQ confirms onboarding is just for setup, not blocking — I can use the system without it.

**My verbatim thought at this point:** "Okay so I can't call Sarah because I don't have her number. I have to text Mike back first to get it. And when I do call her, I can't offer to show her a house, I have to offer a consult so she can sign a rep agreement. That's two non-obvious things I'd have gotten wrong without this."

### What worked

- The `01_lead_qualifier/reference/first-contact-playbook.md` "Referral Text" section is a perfect match for Mike's situation — almost copy-paste-ready scripts.
- The NAR 2024 buyer rep rule is surfaced loudly and repeatedly. As a non-realtor, I'd have walked right into a compliance landmine.
- The compliance flags in the orchestrator (fair housing, "is this area safe / good for families") are clear and well-explained. I now understand why I shouldn't describe East Austin as "good for dog owners" or whatever.
- The handoff packet template gave me a clear list of what info I'm missing (representation status, contact method, language preference).
- The FAQ is genuinely useful — "It asked me 6 questions, can I skip that?" is exactly what I'd want to ask.

### What confused or slowed me down

- The README has a "Typical Flow" example using a Sarah Jones lead. My real lead is also named Sarah Jones. I genuinely paused, thinking the README was somehow about my lead. Pick a different example name.
- The README is dense and front-loads a LOT (routing diagram, specialists table, handoff packet shape, operating principles, customization list, submission writeup, power-user prompts). On my first read I scrolled past the actual "how do I use this for a lead?" instinct because there's so much meta-information first. The "Every-Day Use" section is the right place but it's only four lines and gets buried.
- "Drag the folder into Claude Projects" is the setup, but I'm not sure what `profile.md` is supposed to look like or whether I need to do `start onboarding` BEFORE Sarah or after. The FAQ clarifies but only after I went looking.
- Acronyms (TREC, IABS, TXR-1501, MLS, NAR) appear without a glossary. I had to infer NAR from context. A "Real Estate Terms Glossary" file would help.
- The first-contact script assumes I'll text the referrer to get Sarah's number — but Mike already said "she's expecting your call." There's no script for "referrer punted but didn't give contact info, what now?" Minor but real.

### What I would do next as Maya

1. Reply to Mike: "Thanks for the intro! Got it. What's Sarah's best number or email? I'll reach out today."
2. Once I have Sarah's contact: text her first (lower friction than a cold call from an unknown number), say Mike sent me, set a quick 15-minute call to talk through what she's looking for AND walk her through the buyer rep agreement before any showings.
3. On the call, work the playbook's buyer intake fields: confirm timeline (Oct), budget ($750K), areas (East Austin + alternatives?), must-haves (3BR, yard, dog), pre-approval letter from her credit union, current agent relationship (none, per Mike), language preference.
4. Hand off to Diana for the call/consult — I'm not licensed and the playbook says representation discussions require a licensed human.
5. Tell Diana by lunch: "System is useful. It caught two things I'd have done wrong: (a) Sarah needs to sign a rep agreement BEFORE any showing, (b) I shouldn't characterize East Austin in protected-class language."

### What's missing or unclear from a stranger's POV

- No glossary of real estate jargon. TREC, NAR, IABS, MLS, TXR-1501 all assume the reader knows the field.
- No explicit "If you're the assistant, not the realtor" path. Maya isn't licensed. The playbook is written for the agent, but says "human review required" — it doesn't clearly say "you, the assistant, draft and hand to Diana." I had to infer my role.
- No "what does Sarah's first reply LOOK like" — a sample SMS or call opener for the assistant's situation would be helpful (the playbook gives scripts for the agent, not for an assistant relaying on the agent's behalf).
- The "Drag back the profile.md" loop in setup is described but not shown. I don't know what a finished profile.md looks like, so I'm not sure when I've done it right.
- It's not obvious WHERE the orchestrator's "compliance flags" output ends up. The system says "every routing output must include these flags" but as the user, do I read them, ignore them, archive them? Tell me.

### Verdict

**Yes, with caveats.** A non-realtor, AI-comfortable stranger CAN use this cold and would produce a defensibly correct first response to a real lead — the NAR rep agreement catch alone is worth the setup time. The orchestrator + lead-qualifier flow is genuinely well-structured and the referral script is plug-and-play. The caveats: the README front door is overstuffed and buries the "do this now" path under meta-information; a stranger will trip on jargon (TREC, IABS, MLS, TXR) without a glossary; and the assumed reader is the realtor, not the assistant, which leaves a small but real role-confusion gap. With a 20-line "first lead in 5 minutes" cheat-sheet at the top of README, a glossary file, and a non-Sarah-Jones example in the typical flow, this would be excellent for a stranger. As shipped, it's good — I'd hand it back to Diana saying "this is keeping us, fix the README front door before onboarding the rest of the team."

## Fixes Applied Based On This Test

The system was updated after this transcript was captured. Specific changes:

1. **Name collision fixed.** The README's "Typical Flow" example was renamed from "Sarah Jones" to "Alex Chen." A team member running the test with a real Sarah Jones lead will no longer get confused.
2. **Glossary added.** [`GLOSSARY.md`](GLOSSARY.md) at repo root, defining TREC, IABS, MLS, NAR, TXR-1501, EMD, CD, CMA, DOM, POA, HOA, and ~15 other terms. Linked from README.

## Open Items For v1.1 (deferred)

These findings are real but not addressed in v1 — documented here for the next iteration:

1. **README front-door density.** The 5-minute setup is at the top, but the rest of the README runs long before a stranger sees the "Every-Day Use" examples. A 20-line "your first lead in 5 minutes" cheat-sheet above the diagram would help. Will land in v1.1.
2. **Assistant vs. agent role clarity.** The playbook is written for the licensed agent. A new `00_orchestrator/reference/assistant-vs-agent-roles.md` would explicitly enumerate which actions an unlicensed assistant can do vs. which must route to Diana. Will land in v1.1.
3. **Sample completed profile.md.** Currently `_user_data/profile.md` is a placeholder. A `_user_data/profile.example.md` showing what a finished one looks like would close the "what does done look like" gap. Will land in v1.1.
4. **Compliance flags destination.** The orchestrator outputs compliance flags but the README doesn't say what the user does with them. Brief addition: "Read them, copy any that say `Needs broker review` into your deal-file note for that matter, otherwise they're advisory." Will land in v1.1.
5. **"Referrer didn't share contact" script.** The first-contact playbook assumes the referrer either gives contact info OR is asked for it. The middle case ("she's expecting your call" with no number) needs a specific script. Will land in v1.1.

## What This Test Proves

- The system CAN be used by a non-realtor cold. The verdict is yes-with-caveats, not no.
- The NAR buyer rep gate is the single most valuable catch the system makes for a non-expert user. Worth the setup just for that.
- The handoff packet structure works as a "what info is missing" surface. The tester used it to identify the contact-info gap, not just for handoffs.
- The fair-housing compliance scan is interpretable. A non-realtor came away understanding why protected-class language was a problem.

## Recommended Next Test

A human stranger test with a real non-realtor (10-15 minutes, recorded or transcribed). Compare the human's friction points to Maya's. If they overlap, prioritize the open items above. If they diverge, the human findings take priority.
