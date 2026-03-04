# Space Invaders (3ETI Project)

Academic project developed by **Jules Grivot-Pelisson** and **Raphael Dziopa**.

GitHub Repository: https://github.com/Jules-GP/SI-CPE

---

## Overview

This project is a custom implementation of the classic *Space Invaders* game, developed as part of the CS-DEV coursework.

The game was built using:

* Python
* Object-Oriented Programming
* Tkinter for GUI
* JSON for persistent data storage

We extended the traditional gameplay by introducing additional mechanics and structured architecture.

---

## Gameplay Features

* Player movement both horizontally and vertically (within a restricted area)
* Progressive difficulty: game speed increases at each stage
* New enemy types appear in later stages with higher point values
* 5 starting lives
* Enemies deal:

  * 1 damage (standard shooters)
  * 2 damage (Boss enemies)
* Persistent leaderboard system
* Hidden cheat codes (see below)

The vertical movement mechanic allows more advanced strategic positioning compared to the classic version.

---

## Cheat Codes

The following cheat codes were originally used for debugging and remain hidden in the game:

* `dead` → Eliminates all enemies and skips the current stage
* `help` → Grants +1 HP
* `ez` → Jumps directly to stage 27

---

## Project Structure

```
.
├── database/
│   └── score.json          # Stores player names and scores
│
├── divers/
│   └── Vector.py           # 2D Vector class and vector operations
│
├── game/                   # Core game logic and entities
│
├── managers/               # Managers handling repetitive logic
│
├── ressources/             # Game assets (images)
│
├── screens/                # Tkinter display screens
│
└── main.py                 # Entry point (run this file)
```

To launch the game:

```bash
python main.py
```

---

## Architecture Details

### JSON Database

A JSON file (`score.json`) is used to store player scores persistently.
Scores are saved at the end of each game session and remain available even after the program is closed.

---

### Vector System

A custom 2D `Vector` class was implemented to handle position and movement calculations throughout the game.

Because the environment is fully 2D (x, y), vector manipulation is central to movement, collision, and rendering logic.

A `CoolDown` class was also created to prevent shooting spam.

---

### Game Elements

Each entity in the game (player, enemies, projectiles, walls, etc.) is represented by its own class containing:

* Position
* Sprite
* Health points
* Entity-specific behavior

---

### Core Game Logic

Main logic is handled by:

* `Board.py`
* `GameLogic.py`
* `StageManager.py`

These modules manage:

* Enemy matrix structure
* Stage progression
* Game state updates
* Interaction between entities

---

### Managers

To ensure clean separation of responsibilities, multiple managers were implemented:

**Input Manager**

* Detects keyboard input each frame
* Transmits active inputs to the game logic

**Load Manager**

* Preloads images and assets before the game starts
* Reduces in-game latency

**Render Manager**

* Updates all moving entities every frame
* Clears and redraws elements at updated positions

**Score Manager**

* Handles reading and writing to the JSON database
* Updates leaderboard data

---

### Tkinter Screens

The `screens` directory contains all Tkinter-based display logic, including:

* Menu screen
* Game screen
* Leaderboard screen

---

## Technical Highlights

* Object-Oriented design
* Modular architecture
* Separation of concerns (logic / rendering / input / persistence)
* Custom data structures (enemy matrix list-of-lists)
* Real-time frame updates
* Persistent leaderboard system

---

## Bibliography & Assets

Some graphical assets used in the project were sourced from:

* ArtStation
* PNGFind
* Behance
* Freepik
* Pinterest

(See original repository for detailed links.)

---

## Disclaimer

This project was developed for educational purposes only.
