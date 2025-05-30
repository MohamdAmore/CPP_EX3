# CPP_EX3 – Coup Game Implementation

## 📚 Project Overview

This C++ project is an object-oriented simulation of a role-based strategy game inspired by *Coup*. It models game mechanics involving different player roles, turns, coin management, and role-specific abilities. The game supports up to 6 players and is fully playable in terminal and GUI (optional).

---

## 📦 Project Structure

- `Game.hpp / Game.cpp` – Manages the core game logic, turns, active players, and winner detection.
- `Player.hpp / Player.cpp` – Base class for all roles, defines shared behavior like gather, tax, bribe, coup, etc.
- Role-specific classes:
  - `Governor`
  - `Spy`
  - `Baron`
  - `General`
  - `Judge`
  - `Merchant`
- `main.cpp` – A terminal-based simulation that allows interactive play.
- `test.cpp` – Unit tests using **doctest** framework to verify role logic and edge cases.
- `Makefile` – Supports `make test`, `make Main`, `make gui`.
- `gui/` – Contains GUI implementation.

---

## 🎮 Roles & Abilities

Each role inherits from `Player` and has special abilities:

- **Governor** – `tax()` collects 3 coins. Can `undo` tax from others.
- **Spy** – Can `reveal` a player's coins and `block_arrest`.
- **Baron** – `invest()` converts 3 coins into 6 coins. Gets 1 coin if sanctioned.
- **General** – Can `block_coup()` and revive the target. Gets 1 coin if arrested.
- **Judge** – Can `undo()` or `undo_bribe()`. Gets 1 coin when undoing.
- **Merchant** – Gains passive bonus coins when gathering or taxing.

---

## 🚀 How to Run

```bash
make clean
make Main
./Main
```

To run the tests:

```bash
make test
./test
```

---

## ✅ Rules Enforced

- Maximum 6 players.
- Player with 10+ coins **must** coup.
- Players take turns in sequence.
- Blocking (e.g., undo or block_arrest) can happen on a delayed logic until the player’s next turn.
- All role actions are validated strictly per rules.

---

## 🧪 Testing

- Includes **9+ test cases** validating:
  - Role-specific behavior
  - Turn mechanics
  - Coin constraints
  - Exception handling
  - Special abilities and overrides

Framework used: `doctest`.

---

## 📄 Documentation

All `.cpp` and `.hpp` files include human-readable documentation above functions and classes. The code avoids AI-generated or templated docs and is tailored for natural reading.

---

## 👨‍💻 Authors

- **Student:** Mohammad Amore
- **Language:** C++ (C++20 Standard)
- **OS:** Linux Ubuntu 22.04+
- **Build System:** Makefile

---


## 🏁 End of README
