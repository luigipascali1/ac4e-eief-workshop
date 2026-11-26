# Verification criteria

Linked from [`AGENTS.md`](../../AGENTS.md). Never say "done", "green" or
"replicates" without a command run or equivalent evidence pasted next to the claim.

## 1. Check command (required)

```bash
python3 -m pytest examples/card-krueger-toy/tests examples/mini-economics/tests
```

All collected tests pass (45 at the time of writing). Keep this command identical in
`AGENTS.md`, [`replication/README.md`](../../replication/README.md) and issue cards.

## 2. Expected numbers (when analysis code changes)

```bash
python3 examples/card-krueger-toy/src/did_analysis.py
python3 examples/card-krueger-toy/src/panel_workflow.py
```

| Script | Must print |
| --- | --- |
| `did_analysis.py` | NJ change 2.0, PA change −1.0, toy DiD 3.0 FTE |
| `panel_workflow.py` | Row counts 47 → 43 → 42 → 36 (18 stores); baseline DiD 2.875 |

A changed number is a finding to report, not a test to update.

## 3. Diff checks (every PR)

- [ ] Only the files allowed by the issue card changed.
- [ ] `examples/card-krueger-toy/data/` and `tests/` are untouched.
- [ ] No older output version deleted or overwritten.
- [ ] Every new sample restriction is written down in `data_notes.md` with its row count.
- [ ] The "synthetic teaching data" caveat is still present in outputs and notes.
- [ ] Every new citation is checked against `references/bibliography.bib`.

## 4. What verification does **not** certify

Passing tests show only that the code reproduces the teaching numbers. Research
design, parallel trends, identification and any causal reading stay with the
researcher. The agent reports evidence; the human signs off.

## Helpers

- Skill `replication-checker` — clean-clone reproducibility audit.
- Skill `loop-on-verification` / sub-agent `loop-verifier` — implement → verify → revise.
- Sub-agent `pr-reviewer` — read-only review of a PR against this file and the card.
