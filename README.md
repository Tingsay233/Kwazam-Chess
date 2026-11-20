# Kwazam Chess

A two-player chess variant built in Java Swing for an Object-Oriented Analysis & Design assignment (2024–2025), structured with the Model–View–Controller pattern.

## The game

Kwazam is played on a 5×8 board by Red and Blue. The board flips after every move so the current player always plays from the bottom.

| Piece | Moves |
|---|---|
| **Ram** | One step forward; at the far edge it turns round and heads back |
| **Biz** | An L-shape (2 + 1), and can jump over other pieces |
| **Tor** | Any distance orthogonally, cannot jump |
| **Xor** | Any distance diagonally, cannot jump |
| **Sau** | One step in any direction; capture it to win |

Every 2 full turns, every Tor becomes a Xor and every Xor becomes a Tor.

Games can be saved to a text file and loaded later.

## Design

- **Model:** `Board`, `Piece` and its subclasses (`Ram`, `RamTurn`, `Biz`, `Tor`, `Xor`, `Sau`), `Move`
- **View:** `View` (main menu, board rendering, flipping)
- **Controller:** `ChessController` (mouse input, turn flow, save/load)
- Each piece overrides `isValid` with its own movement rule (polymorphism); the view observes the board through `Observer`.

## Running it

Requires Java 17 or newer.

```bash
javac *.java
java GameLauncher
```

Run the commands from this folder so the `Chessimages/` sprites are found.

## Team

Hiew Wei Cheng, Ng Jia Huang, Say Si Ting, Tan Jing Yi — each source file lists its authors.
