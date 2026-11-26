# Data and outputs

Linked from [`AGENTS.md`](../../AGENTS.md).

## Raw data are read-only

- `examples/card-krueger-toy/data/*.csv` play the role of raw data here: read them,
  never edit, rename or regenerate them. Scripts write anywhere else.
- In a real project the same rule covers `data/raw/`. Cleaning steps write to
  `data/processed/`; analysis-ready files go to `data/final/`.
- `data/raw/` and `data/private/` are git-ignored and must not be opened by agents
  without explicit, per-task permission (see [`../privacy_boundary.md`](../privacy_boundary.md)).

## Every restriction is documented

Each rule that drops rows or stores gets one line in the folder's `data_notes.md`:
the rule, why, and the count left after it. Skill: `sample-restrictions-note`.
Provenance for any new file: [`templates/provenance_manifest.md`](../../templates/provenance_manifest.md).

## Outputs are versioned, never overwritten

- Tables, figures and paper drafts get a version suffix: `table_did_v1.tex`,
  `table_did_v2.tex`. Make a new version instead of overwriting.
- Never delete an older version, even if superseded.
- Generated tables are checked against the code that produced them
  (`panel_workflow.verify_latex_table_numbers`); see `faults/drifted_table.tex` for
  what drift looks like.

## Languages

The live track is Python. Stata and R equivalents are described in
[`examples/r_stata_equivalence.md`](../../examples/r_stata_equivalence.md) and
[`tool-lanes/research-languages.md`](../../tool-lanes/research-languages.md). For a
Stata project, the check command is usually `stata-se -b do master.do`, and the agent
quotes the end of the log as evidence.
