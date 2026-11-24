# Java Gamble Game

A mini gambling game (dice and coin flip) built with Java. It comes in two versions: **console** and **GUI (Swing)** with animations.

## Features

- Player registration with an age check (**18+ only**)
- Starting deposit and **betting** system
- **Roll a Dice**: three dice with several winning combinations
- **Flip a Coin**: choose Heads or Tails
- Safe input handling: no crash when the player types letters or invalid numbers
- Automatic **game over** when the balance runs out
- End-of-game summary (rounds played, wins/losses, biggest win, profit/loss)

### Extra features in the GUI version

- Animated dice that spin and stop one by one
- Animated coin that flips through the air
- Animated balance that counts up or down, green for a win and red for a loss
- Quick bet buttons: **1/2** and **MAX**
- Buttons are locked while an animation is playing

---

## How to Run

### Requirements

- A **JDK** (includes `javac`)
  - `GambleGUI.java`: Java 8 or newer
  - `Gamble.java` (console): **Java 17 or newer** (uses `random.nextInt(1, 7)`)

Check your version:

```bash
java -version
javac -version
```

### GUI version

```bash
javac GambleGUI.java
java GambleGUI
```

### Console version

```bash
javac Gamble.java
java Gamble
```

---

## Game Rules

### Roll a Dice

Three dice are rolled. Results are checked in priority order (top to bottom):

| Result | Example | Payout |
|---|---|---|
| **Big Win** | 6, 6, 6 | Bet × 10 |
| **Triple Match** | 3, 3, 3 | Bet × 5 |
| **Double Match** | 2, 2, 5 | Bet × 0.25 |
| **Straight** | 2, 3, 4 (any order) | Bet × 1 |
| **Anything else** | 1, 3, 6 | Lose your bet |

> House edge: about **6.7%** in the long run.

### Flip a Coin

- Pick **Heads** or **Tails**
- Correct guess = win your bet amount
- Wrong guess = lose your bet amount
- 50/50 odds

### `GambleGUI.java` layout

| Section | Purpose |
|---|---|
| `DiePanel` | Draws the dice |
| `CoinPanel` | Draws and animates the coin |
| `buildRegistration()` | Registration screen |
| `buildGame()` | Main game screen |
| `rollDice()` / `finishDice()` | Dice logic and animation |
| `flipCoin()` | Coin logic and animation |
| `applyResult()` | Updates the balance with animation |

Theme colors can be changed with the constants `BG`, `CARD`, `GOLD`, `GREEN` and `RED` at the top of `GambleGUI.java`.

## Future Ideas

- [ ] Sound effects
- [ ] Save balance and high scores to a file
- [ ] Slot machine game
- [ ] Option to add more funds when the balance runs out
- [ ] Split the code into separate classes (`Player`, `DiceGame`, `CoinGame`)

---

## 📄 License

Free to use for learning.
