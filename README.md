# Snake Game in x86 Assembly
A classic Snake game implementation in x86_64 Assembly for Linux systems, featuring a leaderboard system and terminal-based graphics.

## Overview

This project implements the classic Snake game in pure Assembly language. The game runs in the terminal using ASCII graphics and ANSI escape codes for colors and positioning. It includes features like:

- Colorful terminal-based graphics
- Real-time keyboard input handling
- Score tracking system
- Persistent leaderboard functionality
- Collision detection
- Random apple placement
- Player name registration

## Technical Details

- **Architecture**: x86_64
- **Platform**: Linux
- **Input**: Arrow keys for movement, 'q' to quit
- **Display**: Terminal-based using ANSI escape sequences
- **File I/O**: Uses system calls for leaderboard persistence

## Prerequisites

- Linux operating system (or WSL)
- NASM (Netwide Assembler)
- GCC (for linking)
- Terminal that supports ANSI escape sequences

## Building the Game

1. Assemble the code:
```bash
nasm -f elf64 snake.asm -o snake.o
```

2. Link the object file:
```bash
ld snake.o -o snake
```

## Running the Game

Execute the compiled binary:
```bash
./snake
```

## Gameplay Instructions

- Use arrow keys to control the snake's direction
- Eat apples (O) to grow longer and increase your score
- Avoid hitting the walls or the snake's own body
- Press 'q' to quit the game then enter to exit the leaderboard screen and terminate the program.
- Enter your name after the game to save your score to the leaderboard

## Game Features

### Snake Movement
- The snake moves continuously in the current direction
- Direction can be changed using arrow keys
- Movement speed remains constant throughout the game

### Scoring System
- Each apple eaten increases the score by 1
- Current score is displayed below the game field
- Score is saved to the leaderboard upon game over

### Leaderboard
- Top 10 scores are maintained
- Scores are persisted between game sessions
- Displays player names and scores
- Automatically updates when new high scores are achieved

## Code Structure

### Key Components
- `section .rodata`: Contains constant data like display characters and messages
- `section .data`: Contains mutable game state variables
- `section .bss`: Contains uninitialized data buffers
- `section .text`: Contains the game logic and functions

### Main Functions
- `_start`: Entry point and game initialization
- `update`: Main game loop and display update
- `newapplepos`: Generates new random apple positions
- `get_player_name`: Handles player name input
- `update_leaderboard`: Manages leaderboard updates
- `display_leaderboard`: Renders the leaderboard

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

## Credits

Created by me as an assignment project demonstrating basic x86 Assembly programming concepts.

## License

Feel free to use and modify this code for educational purposes.


## Future Improvements
- Add difficulty levels
- Add power-ups and obstacles
