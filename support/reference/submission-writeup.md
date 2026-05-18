# Submission Writeup

## 100-Word Version

The Agency is a no-software AI operating desk for a small Austin real estate team. A nontechnical realtor can paste a messy real request and get the next safe step, while reviewers can inspect the specialist folders, handoff rules, Agency Standard, lead/deal logs, and Daily Operating Brief. Plain Markdown keeps it portable across Claude, ChatGPT, Gemini, or another LLM. The `support/` folder holds shared process docs without crowding the required folders. Every handoff stays traceable through Matter ID, confidence, trail, return path, stall trigger, and human review.

The project can be found here: https://github.com/shifteddevlabs/the-agency-real-estate-ai-os.git

## What I Built

A teachable, multi-folder real estate workflow that runs in ordinary AI project files, not custom software. I built it from the JJ AI Studio point of view: AI systems should feel useful before they feel impressive. The five required specialist folders stay visible at the root. `_user_data/` and `lead-deal-logs/` support real use. Setup, reference, Daily Operating Brief, Agency Standard, handoff contracts, and test material live in `support/` so they help without crowding the main path.

## Design Decision

The main design decision is dual-readability. A nontechnical realtor can open the README, paste a normal request, and never think about folder structure. A tech-savvy realtor, assistant, or reviewer can inspect the specialist folders, tune the rules, and evaluate the handoffs. The system is also LLM-agnostic: it uses plain Markdown and ordinary language instead of tool-specific commands.

The second design decision is shared process, specialist-owned signals. The Daily Operating Brief, handoff contract, lead/deal log, and Agency Standard live once in `support/reference/`. Each specialist only owns the signals it contributes, such as lead temperature, source recheck, draft status, or verified deadline.

The third design decision is using the orchestrator as the first safety screen. Real estate mistakes often happen before writing starts: wrong owner, missing source, stale status, fair-housing wording, or unverified deadline.

## Next Upgrades

I would record a short Loom walkthrough for Claude, ChatGPT, Gemini, and any other target LLM so a user can see exactly how to load and run the folder. After that, I would add Austin-specific source packs, more transaction checklist templates, a Spanish-language human-review path, and a scored agent-test report showing handoff quality before real team use.
