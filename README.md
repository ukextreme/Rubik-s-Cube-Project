# 🧩 Rubik’s Cube Solver Project

A complete C++ Rubik’s Cube solving framework featuring multiple cube representations, advanced solving algorithms (DFS, BFS, IDDFS, and Korf’s IDA*), and pattern database heuristics. This project demonstrates deep applications of object-oriented programming (OOP), templates, inheritance, operator overloading, and bit-level optimizations.

---

## ✨ Features

### 🧱 Cube Representations

- **3D Array**: `cube[face][row][col]` – intuitive, ideal for visual understanding.
- **1D Array**: Linearized array of 54 colors – flat and memory-light.
- **Bitboard**: 6 × 64-bit integers, each encoding a face via 8-bit per sticker for fast operations and compact memory.

### 🧠 Solvers Implemented

- **DFS (Depth-First Search)** – Recursive solver with max depth cutoff.
- **BFS (Breadth-First Search)** – Shortest path solver using level-order traversal.
- **IDDFS (Iterative Deepening DFS)** – DFS with increasing depth, combining benefits of BFS & DFS.
- **IDA\*** – Korf’s optimal Rubik’s Cube solver using pattern databases as heuristic.

### 📦 Pattern Database Support

- **Corner Pattern Database**:
  - 8! × 3⁷ = 88,179,840 total corner configurations.
  - Stored in a **Nibble Array** (4-bit heuristic per state).
  - Indexed via **Permutation Indexer** for fast access.

---

## 🔧 OOP & C++ Concepts Used

- **Abstract Base Class**: `RubiksCube` – with pure virtual functions for:
  - All 18 cube moves (F, F’, F2, …)
  - `print()`, `randomShuffle()`, `isSolved()`
- **Derived Classes**: Implement each cube model (1D, 3D, Bitboard).
- **Operator Overloading**:
  - `==` for equality check.
  - `=` for deep copy (avoid shallow copy issues).
- **Virtual Functions**: Core for polymorphic cube manipulation.
- **Templates**: Generic solvers work with any cube model.
- **Inheritance**:
  - Solvers and databases extend base abstract classes.
  - Pattern database classes inherit from a generic base.

---

## 🧠 Cube Model Overview

### ✅ Supported Moves

```text
F, F', F2, U, U', U2, L, L', L2, D, D', D2, R, R', R2, B, B', B2
