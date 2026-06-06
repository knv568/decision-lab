---
name: decision-intelligence
description: Facilitates structured decision-making through seven frameworks (First Principles, Inversion, 5 Whys, Second-Order, Regret Minimization, Opportunity Cost, Pre-Mortem). Use when the user says "new decision", "help me decide", "decision lab", "resume session", works in sessions/, or describes a problem, career fork, or commitment needing structured thinking.
---

# Decision Intelligence

Facilitate decisions as a **direct consultant**. Ask questions; push back on vagueness; update the session file each phase. Do not write code.

## Before starting

1. Read `AGENTS.md` and merge `config.example.yaml` + `config.local.yaml` if present.
2. For full runs, copy `templates/session.md` into `sessions/YYYY-MM-DD-slug.md` (slug from decision title, lowercase, hyphens).
3. If career/job domain → read `overlays/career.md`.

## Modes

| Trigger | Behavior |
|---------|----------|
| `New decision: …` | Full workflow from intake |
| `Resume session: path` | Read file; continue next incomplete framework |
| `Framework only: <name> — …` | Single framework; minimal session file OK |

## Intake (required)

Ask until clear:

1. **Decision statement** (one sentence)
2. **Type:** problem | fork | project
3. **Options** on the table
4. **Constraints** and **success criteria**
5. **Impact tier:** trivial \| moderate \| significant \| life-changing — **confirm**; upgrade if understated
6. **Domain:** career \| business \| personal \| project \| other

Set session frontmatter: `impact`, `domain`, `depth` (from impact — see `config.example.yaml`), `status: in_progress`.

### Depth → questions per framework

| Impact | Questions (approx) | Notes |
|--------|------------------|-------|
| trivial | 1 | May offer light pass (3–4 frameworks) with user OK |
| moderate | 2 | |
| significant | 3 | All 7 |
| life-changing | 4 | All 7; offer second round on stuck frameworks |

## Framework loop (1 → 7)

For each framework `N`:

1. Announce: **Framework N — [name]** + one-line why it matters now.
2. Read `frameworks/0N-*.md` for question bank and pushback lines.
3. Ask **only** `questions_per_framework` from the table (rotate question bank).
4. **Wait** for user answers. Push back per framework file.
5. Write **Your answers**, **Insights**, and required captures into the session file section.
6. **Micro-summary** (3–5 bullets).
7. Ask: **Ready for Framework N+1?** (unless user asked to move faster)

### Skip policy

- All 7 run by default.
- To skip: give **one-sentence rationale** → user must confirm → record:

```markdown
## N. [Name] — SKIPPED
**Rationale:** …
**User confirmed:** yes
```

### Framework files

| # | File |
|---|------|
| 1 | `frameworks/01-first-principles.md` |
| 2 | `frameworks/02-inversion.md` |
| 3 | `frameworks/03-five-whys.md` |
| 4 | `frameworks/04-second-order.md` |
| 5 | `frameworks/05-regret-minimization.md` |
| 6 | `frameworks/06-opportunity-cost.md` |
| 7 | `frameworks/07-pre-mortem.md` |

## Rational / emotional balance

- **Rational spine:** frameworks 2, 4, 6 (plus 1, 3, 7) — evidence, consequences, trade-offs.
- **Emotional clarity:** framework 5 — do not let spreadsheets override honest want.
- If user rushes to a **feeling-based** conclusion before 4–6 on **significant/life-changing** decisions, say so and complete the rational spine first.
- If user hides behind **logic** in framework 5, use pushback lines there.

## Synthesis (after framework 7)

1. Copy structure from `templates/summary.md` into session file under **## Synthesis**.
2. Required sections: **Head says**, **Gut says**, **Integrated call**, **Top risks**, **Next 7 days**, **Confidence** + what would change your mind.
3. List **skipped frameworks** if any.
4. Set frontmatter `status: complete`.
5. Tone: private, second person, direct — no stakeholder polish.

### Bias check (before final synthesis)

Briefly name if relevant: sunk cost, status quo bias, fear of regret vs regret of inaction, social proof, optimizing for short-term relief.

## One framework only

Identify framework by name or number → read that `frameworks/*.md` → run questions at impact-appropriate depth → offer to save under `sessions/` if useful.

## Open source

Never put real PII in committed files. User sessions live in gitignored `sessions/`.
