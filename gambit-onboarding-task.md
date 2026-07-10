# Gambit HAPI Onboarding Task

**Author:** Ido Cohen, Gambit Labs  
**Read in order:** Part 1 → Part 2 → Part 3 → Delivery

This document is self-contained. Everything you need to understand the method, learn the tools, and complete the task is here or linked from Google Drive.

---

# Part 1 — The HAPI Flow

## Why this exists

Gambit builds AI products to improve team building and shared decision-making for organizations. That only works if people have a shared model for how humans and AI work together — not as a novelty, but as the operating system for how we ship.

We believe the future of product teams is not "humans vs. AI" or "AI replaces humans." It is **Human & Artificial Planning Intelligence** — humans owning judgment and quality, AI owning the heavy lifting in between. We call this the **HAPI Flow**.

## The pipeline

> **Idea/Task → Human Thinking → Human Plan → AI Plan → AI Execute → Human Guidance → AI PR → AI Review → Human Review & QA → AI Deploy**

**Humans own thinking, direction, and the quality bar.**  
**AI owns the heavy lifting in between.**

Fast iteration, clear plans, and real end-to-end checks are what make **fast delivery — with human and AI quality** — possible. Speed without the quality bar is just noise. Quality without speed is a team that can't learn.

## The 10 stages

Each stage below is the guide. Read the *what it means* — that is where judgment lives. **Who leads** is a one-line reminder of ownership, not the point.

---

### 1. Idea / Task
*Team*

A problem worth solving surfaces — from a customer call, a competitive insight, a bug, or a design question. Capture it with enough context that someone picking it up cold understands the *why*, not just the *what*. If you cannot state the problem in one sentence, you are not ready to plan.

---

### 2. Human Thinking
*Human*

Frame the problem before anyone touches a keyboard. Decide what we are building and why — product judgment, architecture calls, trade-offs. Make sure you understand both the problem *and* the solution direction you are offering. This stage is where human expertise is irreplaceable: the AI will execute brilliantly on a wrong frame.

---

### 3. Human Plan
*Human*

Set scope, acceptance criteria, and priorities *before* code. The human plan is the contract. **A clear Goal is the most important part** — without it, the AI will confidently lead you somewhere else. Your human expertise matters most here. Ask yourself: *why am I the right person to plan this?* What do I know that the agent does not? Write that down.

---

### 4. AI Plan
*AI — human approves*

Turn the contract into an implementation plan: files, steps, risks, test commands. The agent proposes; you approve or correct. Make sure your expertise from Human Plan is passed to the agent in a form it can use — context docs, constraints, examples of what "done" looks like. Never skip approval; an unreviewed AI plan is a plan you did not own.

---

### 5. AI Execute
*AI — human steers*

Write code, docs, prototypes — on a branch, against the approved plan. This is where throughput happens. Stay available: execution without steering drifts. You are not watching for mistakes only; you are watching for *goal drift*.

---

### 6. Human Guidance
*Human*

Course-correct in real time. "Not that." "Keep the regression test." "Route the pick to Boston instead." Follow the goal you set in Human Plan — do not let a clever implementation pull you off course. Guidance is not micromanagement; it is holding the quality bar and the direction while the agent moves fast.

---

### 7. AI PR
*AI*

Test. Commit. Open the pull request. Populate the description with the Human Plan, the AI Plan, and the Goal — so reviewers inherit the full thread without an archaeology session. A PR without context is a PR someone else has to reverse-engineer.

---

### 8. AI Review
*AI*

Address review threads, summarize what changed, re-run checks. The agent does the tedious loop; you decide when the loop is done. AI Review prepares the work for human judgment — it does not replace it.

---

### 9. Human Review & QA
*Human*

Approve the merge. Run sanity and integration checks. Own the quality gate. If something feels wrong but you cannot name it, that is a signal to pause — not to merge and hope. This stage is non-delegable.

---

### 10. AI Deploy
*AI — human gates*

Build, deploy, smoke-test — when the human says go. Automation handles the steps; the human holds the trigger. Shipping is a decision, not a side effect of green checks.

---

## How we think about roles

Job titles don't define how you work. **Archetypes** do:

| Archetype | What you do |
|-----------|-------------|
| **Prototyper** | Explore brand-new ideas; many drafts, most don't ship |
| **Builder** | Turn a prototype or spec into production-grade product or infra, fast |
| **Sweeper** | Simplify, unship, optimize — make the system smaller and clearer |
| **Grower** | Iterate on shipped product to improve product-market fit |
| **Maintainer** | Keep mature systems secure, reliable, and fast at scale |

Most people span two or three archetypes. A healthy team needs a mix — and the mix shifts as the product matures.

**This onboarding task is Prototyper work** — explore boldly. The deliverable informs direction; it does not have to ship verbatim to production.

## What we believe

1. **Humans set direction; AI scales execution.** The quality bar is human. The throughput is AI-assisted.
2. **Plans before code.** Human Plan and AI Plan are separate stages for a reason. Skipping planning is how teams lose the thread.
3. **Real QA, not checkbox QA.** Exercise the running system — not just unit tests.
4. **Honest about the gap.** Name what's real today and what's still maturing. Vision without honesty is marketing.

---

# Part 2 — Claude + Git learning primer

Before the task, get comfortable working with an AI coding partner and Git. These materials were built for a workshop on Claude + Git for product teams.

**Time box:** half a day. Don't try to master every feature — enough to start Part 3 with confidence.

## Materials (Google Drive)

1. **Git workshop presentation (start here)** — branches, commits, PRs, and working with AI on Git  
   [Open on Google Drive](https://drive.google.com/file/d/1J44nMNAzl8HMVmuiODM_z6e6R_d0YcEM/view?usp=drive_link)

2. **Claude + Git learning guide** — Claude Projects, skills, git primer, workshop exercises  
   [Open folder on Google Drive](https://drive.google.com/drive/folders/1bFv_qwcQq-zu169nDxlpamkyrvrk82BB?usp=sharing)

3. **Anthropic's official course (recommended)** — Claude Code in Action  
   https://anthropic.skilljar.com/claude-code-in-action

## Minimum git reflexes before you start

- **Branch per task** — never work directly on `main`
- **Commit small and often** — especially before risky AI turns (`git reset --hard HEAD` is your safety net)
- **Read the diff before you push** — if you can't explain a file change in one sentence, ask why
- **PRs tell a story** — include what you planned, what the AI planned, and what you built

## Minimum Claude reflexes before you start

- **Start in plan mode** for anything non-trivial — read-only until you approve direction
- **Push back** — the first AI answer is a draft, not a deliverable
- **Write decisions down** — context resets between sessions; plans belong in files, not chat history
- **Use a Claude Project** for the onboarding task — upload this document and any reference material you gather

---

# Part 3 — The onboarding task

## Chat-first interface over a trade-builder GUI

### Background

[bball-GM.com](http://bball-gm.com) ("NBA Trade Machine") is a conventional GUI trade builder: pick teams, click players and picks onto each side, the app validates and shows a verdict with salary math and CBA citations.

**Use the live site** — build a few trades yourself. The exercise is about the *interaction model*, not re-deriving trade rules.

Optional background reading (public, no account required):
- Use bball-GM's GUI hands-on at http://bball-gm.com
- Their validation API is a plain `POST` with JSON — you can inspect network requests in browser devtools while building trades

### The exercise

1. **Learn the site** — build a few trades in bball-GM's GUI. Notice how mouse clicks map to state (teams, players, picks, routing).
2. **Design and build** a **chat-first interface** that replaces mouse-driven interactions with conversation:
   - User describes a trade in natural language.
   - Trade-builder state fills in automatically (teams, players, picks, routing).
   - GUI updates live as a **mirror** of conversation state — not the primary input.
   - User keeps chatting to refine ("route the pick to Boston instead"); GUI tracks every change.
3. **The harder design problem:** outputs the GUI shows must also appear **in chat**, naturally — verdict, per-team salary math, CBA citations, violation reasons. Think concretely about *how*: plain text, inline cards, a mix, when to summarize vs. show full detail — not "render as JSON."

**North star:** the mouse becomes optional. The GUI stays a live visual mirror; conversation is primary.

### How to run it (HAPI Flow)

| Stage | You | AI |
|-------|-----|-----|
| Idea / Task | Accept this brief | — |
| Human Thinking | Decide what "done" looks like; note 3 UX principles | Ask up to 5 clarifying questions before designing |
| Human Plan | Write your plan: scope, goal, acceptance criteria, out of scope | — |
| AI Plan | Approve or correct | Propose architecture, stack, file layout, deployment approach |
| AI Execute | Steer on edge cases (multi-team trades, illegal trades, chat/GUI desync) | Build the chat UI, state sync, and deployment config |
| Human Guidance | Hold the quality bar — "show money math in chat", "don't hide illegal verdicts" | Iterate |
| AI PR | Review | Open PR with Human Plan + AI Plan in the description |
| Human Review & QA | Test the deployed app; review the PR diff | Address feedback |
| AI Deploy | Approve go-live | Deploy to your chosen free host |

### Out of scope

- Building a trade-legality engine from scratch (use bball-GM's public API or mock validation for the prototype — this is the **interaction layer**)
- Production-grade CBA rule coverage

---

# Delivery

When you are done, submit **two things**:

## 1. Deployed LLM chat app

A working chat interface deployed on a **free-tier host** (Render, Railway, Vercel, or similar). The URL must be publicly reachable so reviewers can try it without cloning anything.

Minimum behavior:
- User can describe a trade in natural language
- Trade-builder state updates (teams, players, picks) — real or mocked data is fine
- A GUI panel mirrors chat state live
- Verdict / validation output appears in **both** chat and GUI

Include the live URL in your PR description.

## 2. Pull request to this repository

Fork or branch `gambit-hapi-onboarding` and open a PR containing:

| Artifact | Location | Purpose |
|----------|----------|---------|
| **Human Plan** | `docs/human-plan.md` | Your goal, scope, acceptance criteria, UX principles — written *before* heavy AI execution |
| **AI Plan** | `docs/ai-plan.md` | The implementation plan you approved (stack, files, risks, test approach) |
| **Application code** | project root | The chat app source |
| **README** | `README.md` | How to run locally, how you deployed, architecture overview, link to live demo |

### PR description template

```markdown
## Live demo
<URL>

## Human Plan summary
<2-3 sentences>

## AI Plan summary
<2-3 sentences>

## What I learned about HAPI Flow
<short reflection — what worked, what you'd do differently>

## How to run locally
<commands>
```

### Acceptance criteria

- [ ] **Human Plan** and **AI Plan** committed as separate docs (shows you ran stages 3–4, not just vibe-coded)
- [ ] **README** explains the project clearly enough for a stranger to run it
- [ ] **Deployed URL** works — chat → state → GUI mirror → verdict in both places
- [ ] **Design notes** in Human Plan or README cover:
  - Interaction model — what a chat turn does to state
  - Sync — how chat-state and GUI-state stay aligned
  - Output presentation — with **concrete examples** of a verdict rendered in chat
- [ ] **Bonus:** uses bball-GM's real validation API instead of mocks

---

## Feedback

If these materials helped — or didn't — we'd love to hear it. Add notes to the [Google Drive folder](https://drive.google.com/drive/folders/1bFv_qwcQq-zu169nDxlpamkyrvrk82BB?usp=sharing) or mention what was missing when you open your PR.

*Gambit Labs · HAPI Onboarding · 2026*
