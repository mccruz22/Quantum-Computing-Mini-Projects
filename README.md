# Quantum **2² × 2² Sudoku puzzle** using **Grover's algorithm** (Qiskit)
### Quantum Computing Mini Project 1.1 by Madelyn Esther Cruz

## Overview

We create a quantum circuit to search for bitstrings that encode valid Sudoku solutions, using Grover's algorithm.

### Problem Encoding
- Each Sudoku cell is encoded using **2 qubits** (4 values: 00, 01, 10, 11).
- A 4×4 Sudoku has 16 cells → at most 32 qubits for the puzzle variables.
- Input known cells → 2×unknown values for the variable qubits.

### Oracle
- Marks bitstrings that violate row/column/subsquare constraints.
- Uses ancilla qubits to track whether two cells are equal.

## Code Outline

1. Define a function to compare two qubits for equality and mark if two cells (each 2 qubits) are equal.
2. Define a function to check a list of cells for pairwise conflicts.
3.  Define a function to apply the oracle to the Sudoku grid, which marks the conflicts using the previous function.
    - For each row/column/subsquare, check if any two cells are equal (-> at most 12 ancillas).
4. Apply a diffuser to amplify marked (conflict-free) states.
5. Repeat oracle and diffuser.
6. Measure the probabilities of the variable qubits to find the most probable solutions.
7. Plot the probabilities of the variable qubits.
8. Print the most probable solutions.

## References: 
https://github.com/Qiskit/textbook/blob/aebdd2bc86ddb7a79dd8441d52c839d312ffafbb/notebooks/ch-algorithms/grover.ipynb
