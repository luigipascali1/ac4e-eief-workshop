# Agentic Coding for Economists

Participant folder for the EIEF / Luiss workshop, 26-27 November 2026 (Rome). Eight hours, fourteen ideas, one synthetic example.

Antonio Mele.

The numbers in `examples/card-krueger-toy/` are hand-written teaching data. They are not the Card and Krueger (1994) survey, and they support no research claim.

## Clone

Pick a folder on your laptop first. Then:

```bash
git clone https://github.com/meleantonio/ac4e-eief-workshop.git
cd ac4e-eief-workshop
```

If you ask an agent to get this folder, tell it: Go to https://ac4e-eief-workshop.vercel.app/ and follow instructions.

Zip of this folder: <https://github.com/meleantonio/ac4e-eief-workshop/archive/refs/heads/main.zip>

Before Thursday, follow `docs/prework.md` and `SETUP.md`. The laptop check is `python3 scripts/validate_setup.py`.

## How the folders map to the workshop

| Path | What it is |
| --- | --- |
| `START_HERE.md` | Where you begin |
| `AGENTS.md` | Rules the agent reads |
| `SCHEDULE.md` | The clock |
| `exercises/` | What you do in the room |
| `examples/card-krueger-toy/` | The synthetic Card-Krueger panel used all day |
| `templates/` | Forms you copy |
| `.claude/skills/` | Skills the demos run |
| `sessions/` | What each block covers |
| `demos/` | Prompts used in the room |
| `notes/` | Where you write your answers |
| `docs/prework.md` | Before Thursday |
| `docs/privacy_boundary.md` | The privacy check |

The check command from the slides:

```bash
python3 -m pytest examples/card-krueger-toy/tests examples/mini-economics/tests
```

`examples/mini-economics/` is only there so that command can run. The teaching example is `examples/card-krueger-toy/`.

Friday cards are in `examples/card-krueger-swarm/`. Goal statements are in `examples/card-krueger-goals/`.

This copy does not include instructor timing notes.

Ciao
