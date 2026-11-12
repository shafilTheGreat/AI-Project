# AI-Project

# Solving Sudoku as a Constraint Satisfaction Problem

**Course:** Artificial Intelligence  
**Techniques:** CSP modelling, AC-3 (arc consistency), Backtracking search, MRV heuristic, MAC (maintaining arc consistency)  
**Dataset:** Kaggle Sudoku (`rohanrao`) — `puzzle` and `solution` columns, 81-character strings (`0` = empty cell)

## Objective
Model Sudoku as a CSP and compare three solving strategies on the same puzzles:

| # | Method | Idea |
| :--- | :--- | :--- |
| 1 | **Plain Backtracking** | Fill cells in order, undo on conflict |
| 2 | **AC-3 + Backtracking** | Prune domains once with AC-3, then plain backtracking |
| 3 | **AC-3 + MRV + MAC** | Pick the most constrained cell, re-run AC-3 after every assignment |

## Notebook Outline
1. Setup and configuration
2. Data loading
3. CSP formulation
4. AC-3 algorithm
5. Search algorithms
6. Demonstration on one puzzle
7. Benchmark (regular puzzles)
8. Benchmark (hard puzzles)
9. Visualisation
10. Discussion


 Discussion
Fill this section using the tables and charts produced above.

What to compare

Search effort — average and maximum backtracks per method (hardware-independent).
Runtime — average time per puzzle. AC-3 adds work at every node, so on easy puzzles its overhead can outweigh the savings; on hard puzzles the saved search usually matters more.
Reliability — how many puzzles each method solved within the node limit.
Why the methods behave differently

Plain backtracking only detects a conflict when it is about to place a clashing value, so it explores many dead ends.
AC-3 removes impossible values before any guessing, shrinking the search space; many easy puzzles are solved by AC-3 alone (Section 6).
MRV branches on the cell with the fewest options, so wrong guesses fail quickly.
MAC re-runs propagation after every guess, so a wrong guess is usually detected immediately instead of several levels deeper.
Conclusion Summarise in 2–3 sentences which combination performed best on your data, and support it with the numbers from Sections 7 and 8.
