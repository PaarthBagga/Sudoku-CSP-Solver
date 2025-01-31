# 🧩 Sudoku Solver using AC-3 and Backtracking

## 📌 Overview

This project implements a **Sudoku Solver** using:

- **AC-3 (Arc Consistency 3)** for constraint propagation.

- **Backtracking search** for filling in remaining values if AC-3 doesn't fully solve the puzzle.

- **Matplotlib** to visualize the queue length at each step of AC-3 execution.

The solver reads a **9×9** Sudoku puzzle from a file and attempts to solve it efficiently.

## 🛠️ Tech Stack

- Language: Python
- Libraries: matplotlib
- Technologies: Git

## 🔄 Algorithm

### 1️⃣ Read Puzzle Input

- The program reads a Sudoku puzzle from a text file.

- The puzzle should be formatted as a 9×9 grid of numbers, where 0 represents empty cells.

### 2️⃣ Initialize Domains

- Each empty cell is assigned a domain {1-9}, representing possible values.

- Cells with predefined values have a domain of {value}.

### 3️⃣ Apply AC-3 Algorithm

- AC-3 enforces arc consistency by iteratively refining cell domains based on constraints.

- If a cell's domain is reduced to one value, that value is assigned.

- If AC-3 results in an empty domain, the puzzle is unsolvable.

- Queue length at each step is recorded and plotted using Matplotlib.

### 4️⃣ Check for Completion

- If AC-3 fully solves the puzzle, the solution is displayed.

- If not, the solver proceeds to Backtracking.

### 5️⃣ Apply Backtracking Search

- Selects an empty cell.

- Tries assigning values from its current domain.

- Recursively explores solutions while maintaining consistency.

- If a conflict arises, it backtracks to the previous step.

### 6️⃣ Plot Queue Length

- The queue length at each step of AC-3 is plotted to analyze constraint propagation efficiency.

### 7️⃣ Output the Solution

- The final solved Sudoku board is displayed.

- The queue length visualization graph is generated using Matplotlib.

<hr>

## 🚀 Installation & Usage

### 📌 Prerequisites

Ensure you have:

- Python 3.8+ installed.

### 🔧 Installation

Run the following command to install the required dependencies:

```bash
pip install matplotlib
```

### ▶️ Running the Program

1. Drag and Drop a Test Case
  - Open the test_cases folder.
  - Drag and drop a test case file (.txt) into the main folder before running the script.
  - Ensure only one test case file is in the main folder before running (top most directory).

2. Run the Sudoku solver:
```
python sudoku_solver.py test_cases/example_sudoku.txt
```
<hr>

## 📈 Queue Length Visualization

The AC-3 algorithm's queue size is recorded at each step and visualized using matplotlib.

### Example Output Plot

![image](https://github.com/user-attachments/assets/021a174f-817a-45de-aada-e1fa352ad51a)

The plot helps in analyzing how the queue length changes over time:

- **Initial Growth:** The queue size increases as constraints are added.
- **Peak Point:** Maximum constraints are present before reduction begins.
- **Decline:** Constraints are gradually resolved, reducing the queue.
- **Completion:** The queue eventually empties as AC-3 finalizes consistency.

  <hr> 

  ## 🔍 Code Overview
  
### **📝 Key Functions**
| Function | Description |
|----------|------------|
| `read_puzzle(file_path)` | Reads a sudoku puzzle from a file. |
| `print_board(board)` | Displays the sudoku grid. |
| `get_peers(row, col)` | Returns all peer cells for a given cell. |
| `initialize_domains(board)` | Sets possible values (domains) for each cell. |
| `ac3(board, domains)` | Runs the AC-3 algorithm, **records queue length**, and plots the queue size. |
| `revise(domains, cell, peer)` | Removes inconsistent values from a cell’s domain. |
| `find_empty(board)` | Finds the next empty cell in the grid. |
| `backtrack(board, domains)` | Uses backtracking to fill in remaining empty cells. |
| `is_consistent(board, row, col, val)` | Checks if value validity for a given cell. |
| `plot_queue_length(queue_size)` | **Plots queue size over AC-3 execution.** |
| `solve_sudoku(file_path)` | Integrates all functions to read, solve, and display the puzzle. |
  

