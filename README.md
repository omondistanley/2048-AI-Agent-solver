# 2048 Puzzle AI Solver

This project implements an AI agent to play the game [2048](https://en.wikipedia.org/wiki/2048_(video_game)) using advanced search and heuristic techniques. The AI agent is designed to play optimally and reach high tile values automatically.

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [How It Works](#how-it-works)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [AI Approach](#ai-approach)
- [Customization](#customization)
- [References](#references)

---

## Features

- **AI Agent**: Uses expectiminimax search with alpha-beta pruning and heuristics.
- **Random Computer Moves**: Simulates the computer's random tile placement.
- **Terminal Display**: Shows the board state after each move.
- **Configurable Board Size**: Default is 4x4, but can be changed.
- **Time-Limited Moves**: Each AI move is computed within a strict time limit (0.2s).
- **Output Logging**: Maximum tile achieved is logged to an output file.

---

## Project Structure

```
2048-AI-Solver/
├── BaseAI.py             # Abstract base class for AI agents
├── BaseDisplayer.py      # Abstract base class for display
├── ComputerAI.py         # Handles computer's random tile placement
├── Displayer.py          # Handles terminal display of the board
├── GameManager.py        # Main game loop and logic
├── Grid.py               # Board representation and movement logic
├── IntelligentAgent.py   # The main AI agent (player)
├── output.txt            # Output file for results
├── output1.txt           # Additional output file
├── output2.txt           # Additional output file
```

---

## How It Works

- The game alternates between the **player AI** and the **computer**.
- The **player AI** selects moves (up, down, left, right) using expectiminimax search and heuristics.
- The **computer** randomly places a 2 or 4 tile on an empty cell.
- The game continues until no moves are possible or a time limit is exceeded.

---

## Getting Started

### Prerequisites

- Python 3.6 or higher

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/omondistanley/2048-AI-Agent-solver.git
   cd 2048-AI-Solver
   ```

2. **(Optional) Create a virtual environment:**
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **No external dependencies required.**

---

## Usage

To run the AI solver:

```bash
python GameManager.py
```

- The game will play automatically in the terminal.
- The maximum tile achieved will be printed and appended to `output2.txt`.

---

## AI Approach

The **IntelligentAgent** uses the following techniques:

- **Expectiminimax Search**: Handles both deterministic (player) and stochastic (computer) moves.
- **Alpha-Beta Pruning**: Reduces the search space for efficiency.
- **Iterative Deepening**: Increases search depth within the time limit.
- **Heuristics**: Evaluates board states using:
  - Number of empty cells
  - Monotonicity (smoothness of tile values)
  - Smoothness (difference between neighboring tiles)
  - Maximum tile value

---

## Customization

- **Board Size**: Change the `size` parameter in `GameManager`.
- **Output File**: Change the filename in `GameManager.py` if needed.
- **Heuristics**: Modify or extend the `heuristicValue` function in `IntelligentAgent.py`.

---

## References

- [Expectiminimax Algorithm](https://en.wikipedia.org/wiki/Expectiminimax)
- [2048 Game Mechanics](https://en.wikipedia.org/wiki/2048_(video_game))
- [AI for 2048 (Theresa Migler)](https://theresamigler.com/wp-content/uploads/2020/03/2048.pdf)
- [Stanford CS221: Games](https://web.stanford.edu/class/archive/cs/cs221/cs221.1186/lectures/games1.pdf)

---
