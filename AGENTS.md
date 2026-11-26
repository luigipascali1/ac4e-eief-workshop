# AGENTS.md — AC4E EIEF / Luiss workshop

Rules every coding agent reads before it starts. Keep this file short; detail lives in
[`docs/agents/`](docs/agents/).

## Project

Participant repository for **Agentic Coding for Economists** (EIEF / Luiss, Rome,
26–27 Nov 2026, eight hours in four slots). The running example is a **synthetic**
Card–Krueger (1994) minimum-wage panel: NJ vs eastern PA fast-food employment
before and after NJ's April 1992 increase, analysed with an unweighted 2x2
difference-in-differences. The numbers are hand-written teaching data and support
**no research or causal claim**. Claude Code is the primary demo lane; Codex and
Cursor are parallel lanes.

## Folder map

| Path | What it holds | Agent may edit? |
| --- | --- | --- |
| `examples/card-krueger-toy/` | Teaching example: `data/`, `src/`, `tests/`, `faults/`, `data_notes.md` | `src/` and notes only; **never** `data/` or `tests/` |
| `examples/card-krueger-swarm/`, `card-krueger-goals/` | Issue cards and goal statements | Only when the card says so |
| `examples/mini-economics/` | Second test target so the check command runs | Rarely |
| `exercises/`, `demos/`, `sessions/`, `slides/` | Workshop materials | Only when asked |
| `notes/` | Participant answers | Yes |
| `templates/` | Forms to copy (never fill in place) | No |
| `docs/` | Briefs, privacy boundary, rubric; `docs/agents/` = agent workflows | When asked |
| `.claude/`, `.agents/`, `agent-harness/` | Skills, sub-agents, hooks, MCP per tool lane | When asked |
| `references/bibliography.bib` | Bibliography | Add entries only after verifying them |
| `replication/` | How to reproduce from a clean clone | When the verify command changes |

## Hard rules

- Do not modify raw data.
- Do not let agents certify identification, causality, or interpretation.
- Do not ask agents to read `data/raw/`, `data/private/`, or `.env`.
- Never edit a test to make it pass. Never add significance stars to toy tables.
- No secrets, confidential manuscripts, or restricted data in prompts, commits or
  cloud agents. Check [`docs/privacy_boundary.md`](docs/privacy_boundary.md) first;
  for autonomous/cloud agents, fill
  [`agent-harness/autonomous_agent_risk_card.md`](agent-harness/autonomous_agent_risk_card.md).
- Use relative paths. Document sources, transformations, units and every sample restriction.
- Output files are versioned (`_v1`, `_v2`, …); never delete or overwrite an older version.

## Version control

Issue → branch → pull request → human review → merge. One issue per branch, small
commits, never commit to `main` directly, never force-push a shared branch.
Details: [`docs/agents/version_control.md`](docs/agents/version_control.md).

## Verification

```bash
python3 -m pytest examples/card-krueger-toy/tests examples/mini-economics/tests
```

Work is done only when this passes **and** you quote its output, the expected toy
numbers still print (DiD 3.0; panel workflow baseline 2.875), and the diff touches
only the allowed files. Passing tests prove reproduction, not identification.
Full criteria: [`docs/agents/verification.md`](docs/agents/verification.md).
Clean-clone setup: [`replication/README.md`](replication/README.md).

## Workflow docs

- [`docs/agents/version_control.md`](docs/agents/version_control.md) — branches, commits, PRs
- [`docs/agents/verification.md`](docs/agents/verification.md) — what "done" means
- [`docs/agents/data_and_outputs.md`](docs/agents/data_and_outputs.md) — raw data, versioned outputs, Stata/Python lanes
- [`docs/issues_tracking.md`](docs/issues_tracking.md) — issue cards and labels
