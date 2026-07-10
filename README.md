# gambit-hapi-onboarding

Self-contained onboarding for **HAPI Flow** — Gambit's **Human & Artificial Planning Intelligence** workflow — plus a hands-on design/build exercise.

Built for candidates and collaborators outside the Gambit monorepo. Everything you need is in this repository.

## Start here

| Order | File | What it is |
|-------|------|------------|
| 1 | [`gambit-onboarding-task.md`](./gambit-onboarding-task.md) | **Main brief** — HAPI vision, learning path, task, delivery requirements |
| 2 | [`git-workshop.html`](./git-workshop.html) | Git workshop slides — open in a browser |
| 3 | [`gambit-claude-guide.md`](./gambit-claude-guide.md) | Claude + Git learning guide |
| 4 | [`claude-git-workshop/`](./claude-git-workshop/) | Workshop exercises, handouts, sample repos |

Read `gambit-onboarding-task.md` top to bottom. Use the other files during **Part 2** of that document.

## Quick open

```bash
git clone https://github.com/gambit-lab/gambit-hapi-onboarding.git
cd gambit-hapi-onboarding

# Slides (macOS)
open git-workshop.html

# Or serve locally if your browser blocks file:// assets
python3 -m http.server 8080
# then open http://localhost:8080/git-workshop.html
```

## What's in this repo

```
gambit-hapi-onboarding/
├── README.md                    ← you are here
├── gambit-onboarding-task.md    ← full onboarding brief (HAPI + task + delivery)
├── git-workshop.html            ← Git + AI workshop presentation
├── gambit-claude-guide.md       ← Claude Code + Git primer
└── claude-git-workshop/         ← workshop materials (handouts, sample apps, exercises)
    ├── README.md
    ├── 05-cheat-sheet.md
    ├── 07-pre-flight-setup-guide.md
    ├── 09-student-syllabus.md
    ├── handouts/
    ├── sample-repo/
    └── streakkeeper/
```

## Delivery (for candidates)

When you complete the task, submit:

1. **Live demo** — LLM chat app deployed on a free host (Render, Railway, Vercel, etc.)
2. **Pull request** to this repo with:
   - `docs/human-plan.md` — your plan *before* heavy AI execution
   - `docs/ai-plan.md` — the implementation plan you approved
   - Application source code
   - `README.md` in your submission folder explaining how to run and deploy

See **Delivery** in [`gambit-onboarding-task.md`](./gambit-onboarding-task.md) for full acceptance criteria.

## External links

- [bball-GM.com](http://bball-gm.com) — reference trade-builder GUI for the exercise
- [Claude Code in Action](https://anthropic.skilljar.com/claude-code-in-action) — Anthropic's free course (recommended)

---

*Gambit Labs · 2026*
