# tiny-chess-01 entry — 4KB Chess Engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/ragnarbv/tiny-chess-01-entry/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/ragnarbv/tiny-chess-01-entry/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A deterministic 4 KB Python chess engine for the [make.fun tiny-chess-01 bounty](https://make.fun/bounty/tiny-chess-01).

## Engine

`main.py` (2,556 bytes, lzma-compressed) implements:
- 0x88 board representation
- PeSTO tapered PST evaluation (midgame/endgame)
- Zobrist hashing (64-bit, deterministic seed)
- Transposition table (2^16 entries, depth/score/flag/best-move)
- Negamax + alpha-beta + iterative deepening (fixed 180k nodes)
- Quiescence search (captures + promotions + checks)
- Null-move pruning (R=3) with TT flag verification
- Late Move Reduction (depth-2 for late quiet moves)
- Principal Variation Search (full window first, null-window rest)
- Aspiration windows (±50cp)
- MVV-LVA capture ordering + killer moves per ply
- UCI protocol compliance

## Run

```bash
python3 main.py
```

Then speak UCI: `uci`, `isready`, `ucinewgame`, `position startpos`, `go`.

## License

SPDX-License-Identifier: MIT
# test
