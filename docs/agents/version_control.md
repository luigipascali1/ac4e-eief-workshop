# Version control for agents

Linked from [`AGENTS.md`](../../AGENTS.md). Git keeps every change reversible; the
human reviews the diff before anything reaches `main`.

## Flow

1. **Issue first.** Every non-trivial change starts from an issue card with a goal,
   allowed files and yes/no acceptance criteria ([`templates/issue_card.md`](../../templates/issue_card.md)).
2. **One branch per issue.** Name it after the card, e.g. `ck-data-cleaning`.
   Never work on `main` directly.
3. **Plan, then edit.** For changes touching more than one file, write the to-do
   list and wait for approval before editing.
4. **Small commits.** One logical change per commit. Message: imperative summary
   line (≤ 72 characters), then a short body saying *why* and naming the issue.
5. **Verify before pushing.** Run the check command
   ([`verification.md`](verification.md)) and paste the result in the PR.
6. **Pull request.** Link the issue, list files changed, paste the verification
   output, and state anything left undone. Label the card `needs-review`.
7. **Human merges.** Agents never merge their own PRs, never approve them, and
   never move a card to `done`.

## Never

- Force-push, rebase or rewrite history on a branch someone else uses.
- Commit `.env`, keys, `data/raw/`, `data/private/`, `outputs/` or `results/`
  (all are in [`.gitignore`](../../.gitignore)).
- Delete or overwrite an earlier version of a final table, figure or paper draft.
- Edit tests, or skip/disable them, to get a green run.
- Mix unrelated changes in one branch.

## Undoing

Prefer `git revert <commit>` (adds an undo commit) over `git reset --hard`
(discards work). If a planted fault from `examples/card-krueger-toy/faults/` is
being practised, do it on a throwaway branch.
