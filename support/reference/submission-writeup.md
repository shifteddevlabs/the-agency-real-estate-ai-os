# Submission Writeup

## 100-Word Version

The Agency is a folder-based AI playbook for a small Austin real estate team, shaped by my JJ AI Studio lens: useful AI should feel practical, calm, and usable by real people. I made the first path simple enough for a nontechnical realtor, while keeping the deeper structure inspectable for power users and reviewers. Plain Markdown keeps it portable across Claude, ChatGPT, Gemini, or another LLM. The `support/` folder keeps setup, reference, and tests available without crowding the required specialist folders. With another week, I'd record Loom walkthroughs for each major LLM and add Austin-specific source packs and transaction templates.

The project can be found here: https://github.com/shifteddevlabs/the-agency-real-estate-ai-os.git

## What I Built

A teachable, multi-folder real estate workflow that runs in ordinary AI project files, not custom software. I built it from the JJ AI Studio point of view: AI systems should feel useful before they feel impressive. The five required specialist folders stay visible at the root. `_user_data/` and `lead-deal-logs/` support real use. Setup, reference, and test material live in `support/` so they help without crowding the main path.

## Design Decision

The main design decision is dual-readability. A nontechnical realtor can open the README, paste a normal request, and never think about folder structure. A tech-savvy realtor, assistant, or reviewer can inspect the specialist folders, tune the rules, and evaluate the handoffs. The system is also LLM-agnostic: it uses plain Markdown and ordinary language instead of tool-specific commands.

The second design decision is using the orchestrator as the first safety screen. Real estate mistakes often happen before writing starts: wrong owner, missing source, stale status, fair-housing wording, or unverified deadline.

## If I Had Another Week

I would record a short Loom walkthrough for Claude, ChatGPT, Gemini, and any other target LLM so a user can see exactly how to load and run the folder. After that, I would add Austin-specific source packs, more transaction checklist templates, and a scored agent-test report showing handoff quality before real team use.
