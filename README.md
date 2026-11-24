# Java Gamble Game

A command-line and graphical gambling simulation written in Java. The project includes a dice game and a coin-flip game, available as a **console application** and as a **Swing GUI** with animations.

This project is intended for educational purposes only. No real money is involved.

## Features

**Core (console and GUI)**

- Player registration with an age check (18+ only)
- Starting deposit and per-round betting
- Dice game with multiple winning combinations
- Coin-flip game with player-selected side
- Input validation that rejects non-numeric and out-of-range values
- Automatic game over when the balance reaches zero
- End-of-session summary: rounds played, wins and losses, biggest win, and net profit or loss

**GUI only**

- Animated dice that spin and settle one at a time
- Animated coin flip
- Animated balance counter with win and loss indicators
- Quick bet controls (1/2 and MAX)
- Controls disabled while an animation is running

## Requirements

- Java Development Kit (JDK) that includes `javac`
  - `GambleGUI.java`: Java 8 or later
  - `Gamble.java` (console): Java 17 or later, as it uses `Random.nextInt(int, int)`

Verify your installation:

```bash
java -version
javac -version
```

## Getting Started

**GUI version**

```bash
javac GambleGUI.java
java GambleGUI
```

**Console version**

```bash
javac Gamble.java
java Gamble
```

## Game Rules

### Dice

Three six-sided dice are rolled. Outcomes are evaluated in the following priority order:

| Outcome        | Example                 | Payout       |
|----------------|-------------------------|--------------|
| Big Win        | 6, 6, 6                 | Bet x 10     |
| Triple Match   | 3, 3, 3                 | Bet x 5      |
| Double Match   | 2, 2, 5                 | Bet x 0.25   |
| Straight       | 2, 3, 4 (any order)     | Bet x 1      |
| No match       | 1, 3, 6                 | Lose the bet |

The expected house edge on the dice game is approximately 6.7%.

### Coin Flip

- The player selects Heads or Tails.
- A correct guess wins an amount equal to the bet.
- An incorrect guess loses the bet.
- Odds are 50/50.

## Code Overview

Structure of `GambleGUI.java`:

| Component             | Responsibility                           |
|-----------------------|------------------------------------------|
| `DiePanel`            | Renders a die                            |
| `CoinPanel`           | Renders and animates the coin            |
| `buildRegistration()` | Builds the registration screen           |
| `buildGame()`         | Builds the main game screen              |
| `rollDice()`, `finishDice()` | Dice logic and animation          |
| `flipCoin()`          | Coin logic and animation                 |
| `applyResult()`       | Updates the balance with animation       |

Theme colors are defined as constants (`BG`, `CARD`, `GOLD`, `GREEN`, `RED`) at the top of `GambleGUI.java`.

## Roadmap

- [ ] Sound effects
- [ ] Persistent balance and high scores
- [ ] Slot machine game
- [ ] Option to add funds when the balance is depleted
- [ ] Refactor into separate classes (`Player`, `DiceGame`, `CoinGame`)

## License

This project is provided for educational use. 
