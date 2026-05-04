# Man of Stick

A two-player local stickman fighting game built with C++ and OpenGL (GLUT). Two stickmen battle it out by jumping and shooting fireballs until one runs out of health — then the winner gets a crown.

---

## Gameplay

- **2 players** share the same keyboard
- Each player has **7 HP**
- Shoot fireballs at your opponent to drain their health
- Last one standing wins — their stickman gets a crown and the loser is displayed as the "MURDERER"

---

## Controls

| Action       | Player 1 (WASD) | Player 2 (Arrow Keys) |
|--------------|-----------------|----------------------|
| Move Left    | `A`             | `←`                  |
| Move Right   | `D`             | `→`                  |
| Jump         | `W`             | `↑`                  |
| Shoot        | `S`             | `↓`                  |

> Shooting fires a fireball in the direction the stickman is currently facing.

---

## Requirements

- C++ compiler (g++ with C++11 or later)
- OpenGL
- GLUT (or FreeGLUT)

### Installing dependencies on Ubuntu/Debian

```bash
sudo apt install freeglut3-dev
```

### Installing on Fedora/RHEL

```bash
sudo dnf install freeglut-devel
```

### Installing on macOS (with Homebrew)

```bash
brew install freeglut
```

---

## Building & Running

```bash
g++ -o game game.cpp -lGL -lGLU -lglut
./game
```

On macOS:
```bash
g++ -o game game.cpp -framework OpenGL -framework GLUT
./game
```

You'll be prompted to enter names for both players in the terminal before the window opens.

---

## Features

- Randomly assigned player colors each game (red, green, blue, magenta, cyan, orange, purple)
- Health bar displayed above each stickman
- Player names rendered above their character
- Fireballs travel across the screen and disappear on hit or leaving the window
- Jump mechanic with auto-gravity (returns to ground after 200ms)
- Win screen with crown animation on the victor
- Loser screen showing the defeated stickman with a "MURDERER" label
- Draw condition if both players die simultaneously

---

## Notes

- The window size is fixed at **900×900**
- Both players share the same machine — no network play
- Player colors are randomized at startup but may occasionally be the same color (both players use `rand()` without a seed, so colors could match)
