# Transportation Problem Solver

This project provides a solution to the **Transportation Problem**, which is a special class of linear programming problems. The goal is to determine the most cost-efficient way to transport goods from multiple suppliers to multiple consumers, subject to supply and demand constraints. 

The solution is implemented using different methods for finding the initial feasible solution and the **Transportation Simplex Algorithm** to optimize the allocation.

## Table of Contents
- [Transportation Problem Solver](#transportation-problem-solver)
  - [Table of Contents](#table-of-contents)
  - [Features](#features)
  - [Methods](#methods)
  - [How to Run](#how-to-run)
  - [Example](#example)
  - [Dependencies](#dependencies)

## Features
- Read transportation problem data from an external CSV file.
- Solve the problem using four different initial feasible solution methods:
  - **Northwest Corner Rule (NWCR)**
  - **Minimum Cost Method (MCM)**
  - **Minimum Row Cost Method (MRCM)**
  - **Vogel's Approximation Method (VAM)**
- Optimize the solution using the **Transportation Simplex Method**.

## Methods
1. **Northwest Corner Rule (NWCR)**:
   - A heuristic method that allocates as much as possible to the northwest corner of the cost matrix, then proceeds row by row.
   
2. **Minimum Cost Method (MCM)**:
   - Allocates resources starting with the cell that has the minimum transportation cost.
   
3. **Minimum Row Cost Method (MRCM)**:
   - For each row, allocates resources to the column with the minimum cost within that row.
   
4. **Vogel’s Approximation Method (VAM)**:
   - A penalty-based approach that minimizes the transportation cost by considering the cost difference in each row and column.

5. **Transportation Simplex Method**:
   - After obtaining an initial feasible solution from one of the methods above, the Transportation Simplex algorithm optimizes the solution by pivoting through the basic feasible solutions until an optimal allocation is found.

## How to Run
1. Make sure you have Python installed (version 3.x recommended).
2. Install required dependencies using `pip`:
   ```bash
   pip install numpy pandas
   ```
3. Prepare the transportation problem data in a CSV file named `transportation_problem.csv`:
   - The first column represents the suppliers.
   - The last row represents the demand.
   - The matrix in between represents the transportation costs.
4. Run the script:
   ```bash
   python transportation_problem_solver.py
   ```
5. The script will print the initial allocations and their respective costs for each method (NWCR, MCM, MRCM, and VAM), as well as the optimized solution after applying the Transportation Simplex Method.

## Example

Here’s an example of the expected CSV file structure (`transportation_problem.csv`):

|       | D1  | D2  | D3  | D4  | Supply |
|-------|-----|-----|-----|-----|--------|
| **S1** | 12  | 13  | 4   | 6   | 500    |
| **S2** | 6   | 4   | 10  | 11  | 700    |
| **S3** | 10  | 9   | 12  | 4   | 800    |
| **Demand** | 400 | 900 | 200 | 500 |        |


The program will process this data and use the different allocation methods to find an optimal transportation plan.

## Dependencies
- **numpy**: For handling arrays and matrix operations.
- **pandas**: For reading the input CSV file and managing the data.
