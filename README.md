# Stone, Paper, Scissors — C++ Console Game

A console-based implementation of the classic **Stone, Paper, Scissors** game, written in modern C++. The player competes against the computer over a player-chosen number of rounds, with round-by-round results and an overall winner summary at the end.

This project was built as a hands-on exercise in structuring a small C++ program using **enums**, **structs**, and **modular functions** rather than a single monolithic `main()`.

---

## 📋 Table of Contents

- [Features](#-features)
- [Demo](#-demo)
- [Project Structure](#-project-structure)
- [Design Overview](#-design-overview)
- [Getting Started](#-getting-started)
- [How to Play](#-how-to-play)
- [Possible Improvements](#-possible-improvements)
- [License](#-license)

---

## ✨ Features

- Welcome banner shown at the start of every game
- Player-configurable number of rounds per game (entered at runtime)
- Turn-based rounds between **Player1** and the **Computer**
- Randomized computer choices using a seeded random number generator
- Per-round result breakdown (choices made + round winner)
- End-of-game summary with total wins, draws, and the overall winner
- Replay loop — play as many games as you like without restarting the program
- Input validation to ensure only valid choices (`1`, `2`, or `3`) are accepted

## 🎮 Demo

```
 ------------------------------------------------
        Welcome to the Stone-Paper-Scissors Game!
 ------------------------------------------------
Enter the number of rounds you want to play: 1

Round [1] begins:

Your Choice: [1]:Stone, [2]:Paper, [3]:Scissors? 1

____________ Round [1] ____________

Player1 Choice: Stone
Computer Choice: Scissors
Round Winner   : [Player1]
_________________________________________

Game Over! Winner: Player1

Do you want to play again? (Y/N):
```

## 📁 Project Structure

```
.
└── Project_1_Solution.cpp   # Single-file implementation of the game
```

The project currently lives in a single `.cpp` file for simplicity, but the code is organized into clear, single-responsibility functions and data structures so it can easily be split into multiple headers/source files as it grows.

## 🧠 Design Overview

| Component | Type | Responsibility |
|---|---|---|
| `enGameChoice` | enum | Represents the three possible moves: Stone, Paper, Scissors |
| `enWinner` | enum | Represents the possible outcomes: Player1, Computer, Draw |
| `stRoundInfo` | struct | Holds the data for a single round (round number, choices, winner) |
| `stGameResults` | struct | Holds the aggregated results for a full game |
| `RandomNumber()` | function | Generates a random integer within a given range |
| `GetComputerChoice()` | function | Produces a random move for the computer |
| `WhoWonTheRound()` | function | Applies game rules to determine a round's winner |
| `WhoWonTheGame()` | function | Compares win counts to determine the overall winner |
| `ChoiceName()` / `WinnerName()` | function | Convert enum values into human-readable strings |
| `ReadPlayer1Choice()` | function | Prompts and validates the player's input |
| `PrintRoundResults()` | function | Displays a formatted summary of a round |
| `PlayGame()` | function | Runs the requested number of rounds and returns aggregated results |
| `StartGame()` | function | Shows the welcome banner, asks for the round count, and manages the replay loop |

This separation keeps game **rules**, **I/O**, and **state** decoupled, making the logic easy to test, extend, or port to another interface (e.g., a GUI) later.

## 🚀 Getting Started

### Prerequisites

- A C++ compiler that supports C++11 or later (e.g., **g++**, **clang++**, or **MSVC**)
- Windows is recommended out of the box, since the project uses `system("cls")` to clear the console. On Linux/macOS, replace this call with `system("clear")` (see [Possible Improvements](#-possible-improvements))

### Build & Run

**Using g++:**
```bash
g++ -std=c++11 -o rps_game Project_1_Solution.cpp
./rps_game
```

**Using Visual Studio:**
1. Create a new **Console App** project.
2. Add `Project_1_Solution.cpp` to the project.
3. Build and run (`Ctrl + F5`).

## 🕹️ How to Play

1. Run the compiled program.
2. Enter how many rounds you'd like to play when prompted.
3. For each round, enter your choice when prompted:
   - `1` → Stone
   - `2` → Paper
   - `3` → Scissors
4. The computer's choice is generated automatically.
5. The round's outcome is displayed immediately after each round.
6. After all rounds are complete, the overall winner is announced.
7. Choose whether to play again (`Y`/`N`).
