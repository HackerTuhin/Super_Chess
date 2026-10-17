# ♛ Super Chess 16×16

**A big-board chess variant with 16 kinds of pieces, a built-in computer opponent, and real check and checkmate rules.**
Play it against the computer, against a friend on the same device, or sit back and watch two computers play each other. It runs entirely in your browser from a single file, with no install, no account and no internet needed.

---

## Description

Super Chess 16×16 takes the classic game of chess and doubles the board to 16×16. Each side commands **64 pieces**: two rows of 16 pawns and two rows of 16 pieces. Besides the six standard chess pieces you get powerful hybrids (Amazon, Chancellor, Archbishop, Unicorn, Centaur, Fortress, Oracle, Rhino) and unusual pieces (Camel, Serpent, Vampire, Guardian) that change how you attack, defend and trade.

Every piece type, apart from the King and the Queen, appears **exactly twice per side**, one on the left half and one on the right half of the board, and always on **opposite square colours**. The armies are mirror images, so the game stays fair.

The computer opponent has four difficulty levels. It looks several moves ahead, goes after unprotected pieces, defends its own, and builds attacks on your King to set up checkmate.

---

## Quick start

1. Download `super-chess.html`.
2. Open it in any modern browser (Chrome, Edge, Firefox, Safari), on a computer or a phone. There is nothing to install.
3. You play **White** (bottom) and move first. Click a piece, then click a highlighted square.

**On a phone:** download the file, open it from your Files or Downloads app, and choose a browser to open it. If it opens as plain text, use the browser's "Open file" option or share the file to the browser.

---

## Features

- **16×16 board** with 64 pieces per side
- **Three game modes**
  - **vs Computer**: you are White, the computer is Black
  - **2 Players**: two people on one device
  - **Computer vs Computer**: watch two computers play, with **Start / Pause / Resume** (a game with no winner after 300 moves is declared a draw)
- **Four computer levels:** Easy, Normal, Hard, Expert
- **Real chess rules:** check, checkmate and stalemate. Illegal moves are never offered.
- **Move history** panel beside the board, showing every move as White | Black rows
- **Legal-move highlights:** green dots for moves, red squares for captures, red King square when in check
- **Zoom** (+ / −) and scrolling for the big board, and the board scales to fit phone screens
- **Built-in rules panel** (the Rules button) with every piece explained
- **Computer thinks in the background**, so you can scroll the board while it plays
- **Safe resets:** the New game button asks for confirmation; mode and level are locked once a game starts

---

## Starting position

Each side has four rows. From the back:

| Row | Contents |
|---|---|
| 1 (back row) | Rook, Knight, Bishop, Chancellor, Unicorn, Guardian, Archbishop, **Queen, King**, Archbishop, Guardian, Unicorn, Chancellor, Bishop, Knight, Rook |
| 2 | Amazon, Camel, Serpent, Vampire, Centaur, Fortress, Oracle, Rhino, Rhino, Oracle, Fortress, Centaur, Vampire, Serpent, Camel, Amazon |
| 3 | 16 pawns |
| 4 | 16 pawns |

Pieces in the second row can't move until the pawns in front of them have moved out of the way (leaping pieces can jump over them).

---

## The pieces

### Standard pieces

| | Piece | Moves |
|---|---|---|
| ♚ | King | 1 square in any direction, never into check |
| ♛ | Queen | Slides any distance in 8 directions |
| ♜ | Rook | Slides any distance straight |
| ♝ | Bishop | Slides any distance diagonally |
| ♞ | Knight | L-shaped leap (1 and 2), jumps over pieces |
| ♟ | Pawn | 1 square forward (1 or 2 on its first move), captures diagonally forward. Promotes to an Amazon on the far rank |

### Special pieces (2 per side each)

| | Piece | Moves |
|---|---|---|
| 👑 | **Amazon** | Queen moves + Knight leaps (the strongest piece) |
| 🏰 | **Chancellor** | Rook slides + Knight leaps |
| ⛪ | **Archbishop** | Bishop slides + Knight leaps |
| 🦄 | **Unicorn** | Knight leaps + Camel leaps |
| 🐴 | **Centaur** | Knight leaps + King steps (1 square any direction) |
| 🏯 | **Fortress** | Rook slides + 1 diagonal step |
| 🔮 | **Oracle** | Bishop slides + 1 straight step |
| 🦏 | **Rhino** | Rook slides + Camel leaps |
| 🐪 | **Camel** | Leaps (1 and 3) in 8 directions, jumps over pieces. Stays on one square colour forever |
| 🐍 | **Serpent** | Up to 4 steps through empty squares, alternating a straight step and a diagonal step; can capture at the end of any step |
| 🧛 | **Vampire** | Slides like a Queen. Instead of moving, it can **convert an enemy Pawn** within 2 squares to your side |
| 🛡️ | **Guardian** | Steps 1 square in any direction and **protects** adjacent friendly pieces (except the King) from capture |

---

## Rules

- **Win** by checkmating the enemy King. **Stalemate** (no legal move, not in check) is a draw, as is the 300-move limit in Computer vs Computer.
- **Check:** a King is in check when an enemy piece could capture it next move. You must get out of check on your move by moving the King, capturing the attacker or blocking a sliding attacker. Leaps can't be blocked.
- **Promotion:** a Pawn reaching the far rank becomes an Amazon automatically.
- **Guardian shield:** any friendly piece (except the King) standing next to your Guardian can't be captured. The Guardian itself isn't shielded by other Guardians, so attack it directly.
- **Vampire conversion:** converts enemy **Pawns only**, within 2 squares. The Pawn stays on its square, joins your side and now moves in your direction. Conversion uses your whole turn, and a Pawn next to an enemy Guardian can't be converted.
- **Blocking:** sliders and the Serpent are stopped by any piece. Knight, Camel and similar leaps ignore everything in between.
- **No castling and no en passant.**

---

## Playing against the computer

| Level | How it plays |
|---|---|
| **Easy** | Mostly random moves. Good for learning the pieces |
| **Normal** | Looks about 2 moves ahead with light attack and defence awareness |
| **Hard** | Looks about 4 moves ahead, searches extra moves when a King is in danger |
| **Expert** | Searches as deep as it can in about 9 seconds per move |

**Under the hood:** the computer is a custom engine written for this game (it is not Stockfish, which can't handle a 16×16 board or these pieces). It uses a negamax search with alpha-beta pruning, iterative deepening, capture ("quiescence") search, and move ordering. It scores positions by material, pawn advancement and how close its strong pieces are to your King. On top of that it checks which pieces are attacked or protected, how safe each King is, and how few escape squares an enemy King has, which is how it hunts for checkmate. Expert and Hard also search extra moves when a King is in check.

Expect it to be decent at tactics and to still make mistakes in the quiet middle game, especially at lower levels. It is a game opponent, not a grandmaster.

---

## Controls

| Action | How |
|---|---|
| Move a piece | Click the piece, then a highlighted square |
| Cancel a selection | Click an empty or non-highlighted square |
| Zoom | **+** and **−** buttons |
| Scroll the board | Drag or use the scroll bars (works while the computer is thinking) |
| Rules | **Rules** button |
| New game | **New game** button, then confirm the warning |
| Change mode | Mode button (before the first move only) |
| Change level | Level dropdown (before the first move only) |

---

## Technical notes

- A single self-contained file: HTML, CSS and JavaScript with no libraries and no network requests.
- The board is drawn on an HTML canvas; pieces are drawn with Unicode and emoji symbols, so their look depends on your device's fonts.
- The computer's search runs in short slices so the page stays responsive.
- Game state lives in memory only, so reloading the page starts a fresh game.

---

## Known limitations

- No save/load, undo or online play. Two-player mode is on one device only.
- No draw by repetition or by the fifty-move rule.
- The computer is strong at short tactics but not at long-term planning.
- Some pieces use emoji, which look different on different devices.
