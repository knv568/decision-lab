# Decision Lab

A Cursor workspace for making better decisions using **seven structured thinking frameworks** — with an agent that asks questions, pushes back, and writes a private synthesis you can revisit.

Inspired by consultant-grade mental models (First Principles, Inversion, 5 Whys, Second-Order Thinking, Regret Minimization, Opportunity Cost, Pre-Mortem).

## Quick start

1. Open this folder in **Cursor**.
2. Start a chat and say:

   ```text
   New decision: [describe your problem or fork in the road]
   ```

3. Answer the agent’s questions **one framework at a time**.
4. Your session is saved under `sessions/` (gitignored — stays on your machine).
5. At the end you get a **private synthesis** (head vs gut, recommendation, next steps).

### Resume later

```text
Resume session: sessions/2026-06-01-my-decision.md
```

### Run one framework only

```text
Framework only: inversion — [context]
```

## How it works

| Piece | Purpose |
|-------|---------|
| `AGENTS.md` | Tells the Cursor agent this is a decision workspace |
| `.cursor/rules/decision-lab.mdc` | Facilitation style (direct, one phase at a time) |
| `.cursor/skills/decision-intelligence/` | Full 7-framework orchestration |
| `sessions/` | Your decision journals (not committed to git) |
| `reference/frameworks-quick-ref.md` | One-page cheat sheet |


## Impact-based depth

The agent adjusts how many questions it asks based on stakes:

| Impact | Typical use |
|--------|-------------|
| Trivial | Low-stakes, reversible |
| Moderate | Meaningful but not life-defining |
| Significant | Job offers, major moves, big bets |
| Life-changing | Career pivots, irreversible forks |

You can always correct the tier during intake.

## License

MIT — see [LICENSE](LICENSE).
