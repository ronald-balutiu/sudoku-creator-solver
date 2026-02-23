# Sudoku Creator Solver

## About
This project was created during my undergrad to better understand Sudoku and strategies for solving NP-hard problems. It is a simple Sudoku app that lets you:

- play puzzles in a GUI
- load and save game states
- generate random boards
- solve boards automatically

## Algorithms Used
The solver is based on two ideas:

1. Searching (depth-first search)
2. Constraint propagation

At each step, it selects the square with the fewest remaining possibilities, tries a value, and propagates constraints by removing that value from peer squares. If this leads to a contradiction, it backtracks and explores another branch. This cuts down the search space significantly compared to brute force.

Board generation reuses the solver:

1. Seed the grid with a random value in a random square.
2. Solve to produce a complete valid board.
3. Remove values one by one and test alternatives.
4. Keep a cell removed only when uniqueness is preserved.

This is how the generator aims to produce puzzles with a single solution.

## Running the Code
Run:

```bash
python sudoku.py
```

The repository also includes 50 pre-made boards in `50 Random Problems/`.
