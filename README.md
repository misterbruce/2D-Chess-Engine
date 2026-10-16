# 2D Chess Engine — Python learning project

A command-line chess implementation developed to explore board representation, piece-specific move generation, rule enforcement, and turn-based game logic.

## What is implemented

The current single-file program (`CEP.py`) contains an 8×8 indexed board, classes for chess pieces, move-generation functions, legal-move checking, a text-based board display, and an interactive command-line game loop. The program also contains experimental testing helpers and notation-related logic.

## Running

Requires Python 3. The script uses Python's standard library.

```bash
python CEP.py
```

**Important:** The module starts an interactive game on import. Run it directly in a terminal rather than importing it into unrelated scripts. Its correctness has **not** been validated against standard chess test suites.

## Engineering notes

- **Representation:** Squares are indexed from 1 to 64, with board-edge lookups and piece objects used to compute moves.
- **Move logic:** Move generation is implemented separately for each piece category; rule checks are interleaved with global game state.
- **Interface:** A terminal loop handles input and prints each updated board position.

## Known limitations

- All code currently lives in a single ~2,100-line module with mutable global state.
- Interactive input, timing delays, rule processing, and move generation are tightly coupled.
- Automated regression tests and a standard test-position suite are not included.
- No claims are made about engine playing strength or full chess-rules compliance.

## Planned improvements

1. Move game initialization under a `__main__` guard to make importing safe.
2. Separate board state, legal move generation, move application, and CLI presentation.
3. Add repeatable tests for castling, check, checkmate, stalemate, promotions, and en passant as applicable.
4. Define a FEN-based test harness and assess correctness before introducing search algorithms.
5. Document any eventual position evaluator or search algorithm with actual performance measurements.

This repository is presented as an ongoing algorithmic learning project, not a finished competitive chess engine.
