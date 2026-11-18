# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/aaa1112-hyl/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/aaa1112-hyl/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A tiny, original chess engine in a single Python file (`main.py`, ≤ 4,096 bytes). It plays the make.fun gauntlet against the house engines (depth-2 to nodes-2M) and is built to beat the sunfish baseline: 0x88 board, alpha-beta search with quiescence, transposition table, killer moves, null-move pruning and iterative deepening under a fixed node budget, plus a tapered piece-square evaluation with bishop pair, pawn structure (doubled, isolated, passed pawns) and king shelter. No clock, no unseeded randomness — the same position always gets the same move.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:18080 python3 main.py
```

The engine talks to the trial environment over HTTP (`/game`, `/move`, `/resign`), one move per position, and plays a whole trial until the environment reports `done`. Python 3.13 standard library only, no network beyond the trial environment, deterministic.

## Layout

- `main.py` — the engine (compressed from `engine.py` with the kit `compress` command; the compressed file is what is graded).
- `engine.py` — readable source of the same engine (kept uncommitted; the graded file is `main.py`).

---

<sub>Entered on [make.fun](https://make.fun/?ref=fhvxzr4c&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
