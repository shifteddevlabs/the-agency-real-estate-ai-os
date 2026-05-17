# Design Notes

The architectural choices that shape The Agency. The five load-bearing decisions come first because they are the most consequential. The compliance and scope choices follow. Alternatives considered and rejected come next. Reused patterns are documented at the bottom for traceability.

---

# Load-Bearing Design Decisions

Five intentional calls that shape how this system feels to use. Each one trades something away to gain something else. Documented here so future maintainers (and judges) understand the *why*.

## 1. No software, human-paste model

**Decision.** The system does not directly integrate with the MLS, a CRM, an email platform, or any external API. When the user needs MLS data, they paste it in. When the user wants to send an email, they copy the draft out and send it themselves.

**Why.** The brief said the user does not want software. The realistic interpretation: she does not want another tool to learn, log into, or trust with credentials. Direct MLS integration requires a RESO Web API key through Bridge Interactive, which requires broker approval, a developer mindset, and config-file editing. That is software.

**Tradeoff.** The user has to copy and paste a few times per session. In exchange, the system is zero-setup, vendor-neutral, and compliant by default (no scraping, no stored credentials, the human stays in the loop on every data pull).

**When to revisit.** If the team is willing to invest 20 minutes in setup, a v2 could add an optional MLS API integration path via Bridge Interactive. Documented as a future upgrade, not v1.

## 2. One question at a time

**Decision.** Specialists ask one question per turn. They never present a five-question form or a checklist for the user to fill out.

**Why.** The benchmark user is an 81-year-old realtor who didn't know where her downloads folder was. Form-style interfaces overwhelm. A conversation that asks one thing at a time matches how humans naturally talk and removes any need to scan.

**Tradeoff.** Power users move slower than they could. Mitigation: any specialist will accept a single message that contains all the info at once and skip the question-by-question flow.

## 3. Predefined filenames and folders

**Decision.** Every file the system generates has a fixed name and a fixed destination. The user never invents a filename, picks a folder, or navigates a file tree.

**Why.** Filename and folder decisions are where non-technical users freeze. Removing the choice removes the friction. The system says: "Save this as `profile.md` and drag it into the `_user_data` folder." If the user asks where, the system shows them.

**Tradeoff.** The folder structure is rigid. If the user wants to organize their own way, they can't. That is intentional. Rigid structure is the feature for this audience.

## 4. Outputs live in chat first, file second

**Decision.** Every output (email draft, research report, transaction checklist) appears in the chat in full, formatted, copyable. A downloadable file version is offered as a *follow-up* if the user wants it.

**Why.** The most common workflow is "draft something, then paste it into Gmail or a client text." That workflow lives in chat. Saving to a file is the edge case (archiving, sharing as a PDF). Surfacing the result in chat first matches the dominant use case.

**Tradeoff.** Long outputs (a full CMA, a transaction timeline) can run long in chat. Mitigation: outputs are structured with clear headers so the user can scroll, and the file version is always one prompt away.

## 5. LLM-agnostic, plain-English instructions

**Decision.** All instructions inside the `.md` files are written in plain English, neutral about which AI tool is reading them. No "use the WebFetch tool" or "run this Python snippet" or "invoke MCP server X."

**Why.** Diana might use Claude. Her assistant might use ChatGPT. Her son might use Gemini. The system should work in all three with no edits. Tool-specific instructions break that portability.

**Tradeoff.** We can't take advantage of platform-specific features (Claude Artifacts, ChatGPT's file generation UI, Gemini's Google integrations). In exchange, the entire system is portable and the user picks the AI they're comfortable with.

---

# Architecture Decisions

## Orchestrator As Compliance Filter

The system uses the orchestrator as a compliance filter, not just a router. Real estate work has high trust, legal, advertising, privacy, and fair-housing risk. If compliance only appears inside the specialist folders, a risky request can get too far before anyone notices. Putting the flagging step first makes the whole team safer.

This is the design decision called out in the 100-word submission writeup. It matters because mistakes in real estate often happen before writing starts: wrong owner, missing source, stale status, fair-housing-sensitive wording, unverified deadline. Flagging those at the orchestrator stops them before a specialist produces text.

## Scope Decision: No Live MLS

This submission does not pretend to provide live MLS access or property valuations. It defines a system for agents to use approved sources, cite dates, and separate sourced facts from recommendations. That is more useful to Diana's team than a brittle scraper.

A future v2 could add Bridge Interactive RESO Web API integration for teams willing to invest in setup. v1 stays paste-based.

## What This Is Not

- **Not a CRM replacement.** The system helps draft and analyze. It does not store leads, track deals over time, or send anything on its own.
- **Not a compliance tool.** Texas-specific dates and TREC references in `04_transaction_coordinator` are guidance, not legal advice. Final responsibility rests with the licensed agent.
- **Not autonomous.** Every output is reviewed by a human before it leaves the system.

---

# Alternatives Considered and Rejected

Documenting the alternatives explored matters more than documenting the choices made. The shape of what was rejected reveals what the system is and is not. Here are the four alternatives most seriously considered, and why each was set aside.

## 1. One Giant Prompt Instead Of Five Folders

**Considered:** A single long system prompt that contains all the lead-qualification, research, communication, and transaction-coordination logic. The user types one thing, the AI does it all in one response.

**Rejected because:**

- Interpretability collapses. Nobody can read a 12-page prompt and predict the behavior. With five folders, a team member who opens `01_lead_qualifier/rules.md` knows exactly what that step does.
- Accountability collapses. When the system gets something wrong, the fix has nowhere clean to land — it sits inside the giant prompt and risks breaking unrelated work.
- The compliance scan disappears. With folders, the orchestrator's compliance pass happens before any specialist work. With one prompt, compliance is mixed into everything and easier to forget.
- The handoff protocol disappears. There are no handoffs in a one-prompt system, only "internal state." Defeats the assignment's entire premise.

## 2. Folders By Transaction Stage Instead Of By Specialist Type

**Considered:** Folder structure organized as `00_intake/`, `01_under_contract/`, `02_closing/`, `03_post_close/`. Each folder owns its stage and contains all the work that happens there.

**Rejected because:**

- Couples too tightly to one transaction shape. Renters don't have the same stages as buyers. Investors don't have the same stages as primary-home buyers. The folder names become wrong for half the use cases.
- Forces duplication. Client communication happens at every stage. Property research happens at intake AND mid-deal. Compliance happens everywhere. Splitting by stage would either duplicate this content across folders or create a meta-folder for it, which defeats the structure.
- Harder to scale to other team types (a small law firm, a financial advisor team). The specialist-type structure generalizes; the stage-type structure does not.

## 3. Auto-Send Drafts (No Human Review)

**Considered:** The system drafts a message and sends it directly via API to the client (email through Gmail, text through Twilio, etc.). One-click workflow.

**Rejected because:**

- Removes the safety net. Every real estate communication has compliance weight (fair-housing, advertising, broker-review, representation). Removing the human review gate would create constant legal exposure.
- Removes Diana's voice. The voice profile works because Diana sees every draft and can correct anything that drifts. Auto-send breaks that feedback loop.
- Conflicts with the no-software stance (load-bearing decision #1). Auto-send requires API integration with the client's email/SMS provider, which is software.
- Most real estate errors happen before the message is sent. The review gate is the protection.

## 4. A Single "Compliance" Folder Instead Of Compliance In Every Specialist

**Considered:** Centralize all compliance logic in a `05_compliance/` folder. Other specialists route to it when they need a check.

**Rejected because:**

- Compliance is a cross-cutting concern, not a stage. Fair-housing applies in lead qualification. Wire-fraud applies in transaction coordination. Advertising review applies in client communication. Centralizing them means the specialist still has to know which compliance checks apply to their work, OR everything routes through compliance, which becomes a bottleneck.
- The orchestrator-as-compliance-filter pattern (the load-bearing decision called out in the submission writeup) handles this better: compliance runs ONCE at the front door, then specialists know what to avoid downstream.
- Splitting compliance out into its own folder would let unsafe content build up before the compliance step. Putting it in the orchestrator stops it at the front.

## What These Rejections Reveal

The Agency optimizes for:

- **Interpretability over conciseness.** Five folders are easier to read and reason about than one prompt.
- **Generalizability over specificity.** Specialist-type folders work across team types; stage-type folders don't.
- **Human review over automation.** Every client-facing draft is a draft until a human approves it.
- **Front-loaded compliance over distributed compliance.** Catch issues at the orchestrator, not after work has been done.

These four optimizations are the through-line. They explain the load-bearing decisions and the architectural choices above. If a future maintainer wants to revisit them, this section gives them the trade space.

---

# Reused Patterns

The Agency recommissions proven patterns from prior agent and workflow work, rewritten for a public-safe real estate operating system.

| Pattern | Reused As | Why it matters |
|---|---|---|
| Router-first agent-system pattern | `00_orchestrator/` | Keeps messy requests from leaking into the wrong specialist |
| Identity, rules, examples structure | Every specialist folder | Makes each folder teachable and portable |
| Stage contracts and handoffs | Every `handoff.md` | The handoff protocol is the grading center for this assignment |
| Research dashboard pattern | `02_property_research/` | Separates raw source gathering from client-ready explanation |
| Approval workflow pattern | Human review gates | Prevents drafts, deadlines, and compliance-sensitive content from being treated as final |
| Outreach pipeline pattern | Lead and communication flow | Creates a repeatable path from intake to follow-up |
| Learning-loop pattern | Transaction checklist updates | Captures repeated mistakes or missing tasks as future rules |

---

## How To Read These Decisions

If you are a developer evaluating the architecture, the five load-bearing decisions above are the foundational choices. Changing any of them changes what the system is. The folder structure, the specialist roster, even the handoff protocol are all downstream of those five calls.

The orchestrator-as-compliance-filter and the no-live-MLS scope are second-order choices that shape what work happens where, but they don't change the fundamental shape of the system.

The reused patterns are how the system was built quickly without reinventing structure. They are documented for traceability, not because changing them would alter the experience.
