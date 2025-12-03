# Lane Dodging Game - Analysis & Enhancements

## Project Information
- **Repository**: https://github.com/shoonyank/game
- **Language**: C (Windows)
- **Game Type**: Console lane dodging game

---

## Objective 1: Game Analysis

### Game Overview
Simple 3-lane dodging game where player avoids falling obstacles. Score increases for each obstacle dodged, speed increases progressively.

### Core Components

**Variables:**
- `x` - Player lane position (0-2)
- `step` - Obstacle vertical position (0-10)
- `obstaclePos` - Obstacle lane (0-2)
- `score` - Points earned
- `speed` - Frame delay (120ms → 40ms)

**Game Loop:**
```
Initialize → Input → Clear → Draw → Collision Check → Update → Repeat
```

**Input Handling:**
- Left Arrow (75) - Move left
- Right Arrow (77) - Move right
- Non-blocking with `_kbhit()` and `getch()`

**Collision Detection:**
```c
if (step == 10 && x == obstaclePos)
    // Game Over
```

**Difficulty Progression:**
- Speed decreases by 5ms per obstacle dodged
- Minimum speed: 40ms (maximum difficulty)

**Current Features:**
- ✅ 3-lane movement system
- ✅ Score tracking
- ✅ Progressive difficulty
- ✅ Restart option
- ✅ Random obstacle spawning

**Current Limitations:**
- ❌ No lives system (instant game over)
- ❌ No high score file storage
- ❌ Platform dependent (Windows only)
- ❌ Screen flickers (system("cls"))

---

## Objective 2: Implemented Modifications

### 1. Lives System (Simple)
Added 3 lives - lose one per collision, game continues until all lost.

### 2. High Score Storage (High-Level - counts as 2)
Saves best score to file, loads on startup, shows "NEW HIGH SCORE!" message.

### 3. Improved Display (Simple)
Shows lives as hearts, high score always visible, better game over screen.

---

## Technical Details

**Libraries Used:**
- `stdio.h` - Input/output
- `conio.h` - Keyboard input
- `windows.h` - Sleep function
- `stdlib.h` - Random, system
- `time.h` - Random seed

**Key Functions:**
- `_kbhit()` - Non-blocking key check
- `getch()` - Get key without echo
- `Sleep()` - Frame delay
- `rand() % 3` - Random lane selection

---

## How to Compile & Run

```bash
# Compile
gcc game.c -o game.exe

# Run
game.exe
```

---

## Controls
- **←** Left Arrow - Move left
- **→** Right Arrow - Move right
- **Menu 1** - Restart
- **Menu 2** - Exit

---

## Enhanced Features Summary

| Modification | Type | Description |
|-------------|------|-------------|
| Lives System | Simple | 3 lives with visual hearts |
| High Score File | High-Level | Persistent storage in highscore.txt |
| Display Updates | Simple | Shows lives, high score, better UI |

**Total: 3 modifications (High-Level counts as 2)** ✅

---

## Files Created
- `game.c` - Enhanced game code
- `highscore.txt` - Auto-generated score file
- `README.md` - This documentation

---

## Author

- **Enhanced**: muskan gautam
- **Date**: December 2025
