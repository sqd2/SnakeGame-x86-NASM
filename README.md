# Snake Game in x86 Assembly
A  Snake game implementation in x86_64 Assembly for Linux, with a leaderboard system and terminal-based graphics.

## Overview
This project implements the classic Snake game in pure Assembly language. The game runs in the terminal using ASCII graphics and ANSI escape codes for colors and positioning. It includes features like:

- terminal-based graphics
- Real-time keyboard input handling
- Score tracking system
- Leaderboard functionality
- Collision detection
- Random apple placement
- Player name registration

## Technical Details

- **Architecture**: x86_64
- **Platform**: Linux
- **Input**: Arrow keys for movement, 'q' to quit
- **Display**: Terminal-based using ANSI escape sequences
- **File I/O**: Uses system calls for leaderboard persistence

## Building the Game

1. Assemble the code:
```bash
nasm -f elf64 snake.asm -o snake.o
```

2. Link the object file:
```bash
ld snake.o -o snake
```


3. Execute the compiled binary:
```bash
./snake
```

## Gameplay Instructions
- Use arrow keys to control the snake's direction
- Eat apples (O) to grow and increase your score
- Avoid hitting the walls or the snake's own body
- Press 'q' to quit the game then enter to exit the leaderboard screen and terminate the program.
- Enter your name after the game to save your score to the leaderboard

## Game Features

### Snake Movement
- The snake moves continuously in the current direction
- Direction can be changed using arrow keys

### Scoring System
- Each apple eaten increases the score by 1
- Current score is displayed below the game field
- Score is saved to the leaderboard upon game over

### Leaderboard
- Top 10 scores are maintained
- Scores are persisted between game sessions
- Displays player names and scores
- Automatically updates when new high scores are achieved


### Terminal Handling

- Uses custom terminal mode settings for real-time input
- Implements proper cleanup to restore terminal state
- Handles ANSI escape sequences for display

## Technical Implementation

The game uses several low-level system features:
- Jumps for conditional and unconditional branching
- Arithmetic operations for score keeping and leaderboard.
- Loops to iterate through the program.
- System calls for file I/O and terminal manipulation
- ANSI escape sequences for terminal graphics
- Non-canonical terminal mode for real-time input
- Binary file I/O for leaderboard persistence

