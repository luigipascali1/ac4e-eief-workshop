# CLAUDE.md

@AGENTS.md

The rules above (imported from [`AGENTS.md`](AGENTS.md)) apply in full. This file
only adds Claude Code specifics.

## Where Claude's pieces live

| Piece | Path |
| --- | --- |
| Skills | `.claude/skills/*/SKILL.md` (portable copies: `agent-harness/claude/skills/`) |
| Sub-agents | `.claude/agents/*.md` — `data-reviewer`, `literature-reviewer`, `pr-reviewer`, `loop-verifier`, `sdd-orchestrator` |
| Hooks | `.claude/hooks/` + `.claude/settings.example.json` (optional) |
| MCP | `agent-harness/claude/mcp/mcp.json.example` → `.mcp.json` (optional, not used in the room) |

## Claude-specific defaults

- Start read-only (plan mode) until the issue's acceptance criteria are clear.
- Delegate reviews to sub-agents explicitly; they are read-only.
- Confidential data: refuse and point to `docs/privacy_boundary.md`.
- CLI smoke check: `claude --version`; record the command in `notes/cli_lane.md`.
