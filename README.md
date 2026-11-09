# Number Game 🎲

A small terminal guessing game written in C. The computer picks a secret number, you try to guess it, and you earn points for guessing in fewer attempts.

It's a classic beginner project for practising C basics: functions, loops, `switch` statements, user input and random numbers.

## How to play

1. Choose how many rounds to play (**1 to 5**). If you enter more than 5, the game asks again.
2. At the start of each round, pick a difficulty level:

   | Key | Level        | Secret number range | Starting points |
   |-----|--------------|---------------------|-----------------|
   | `1` | Simple       | 0 – 9               | 10              |
   | `2` | Intermediate | 0 – 49              | 50              |
   | `3` | Difficult    | 0 – 99              | 100             |

3. Enter your guesses. After each one the game tells you whether you were **too low** or **too high**, and shows what the number was.
4. Each guess costs 1 point. When you guess correctly, the round ends and your score is shown, for example `out of 10 you have 7`.

> **Heads up:** a **new** secret number is picked before every guess, so each guess is a fresh chance rather than a narrowing search. Guesses outside the level's range are rejected with `Wrong input`.

## Getting started

### Requirements

- A C compiler such as `gcc`
- Linux, macOS, or Windows (with MinGW or WSL)

### Build

```bash
gcc -Wall -Wextra -o play igihimba.c amaguru.c
```

### Run

```bash
./play
```

A prebuilt Linux x86-64 binary named `play` may already be in the repo. Rebuild it if it doesn't run on your machine.

## Project structure

The file names are in Kinyarwanda and follow the parts of a body:

| File         | Meaning      | Contents                                                     |
|--------------|--------------|--------------------------------------------------------------|
| `umutwe.h`   | "head"       | Header file: shared includes and function prototypes         |
| `igihimba.c` | "body/trunk" | `main()`: shows the intro and checks the number of rounds    |
| `amaguru.c`  | "legs"       | Game logic: random numbers, input, levels, rounds and scoring |

### Functions

| Function            | Purpose                                                      |
|---------------------|--------------------------------------------------------------|
| `Intro()`           | Asks how many rounds you want to play                        |
| `Rounds(n)`         | Runs `playing()` `n` times                                   |
| `playing()`         | Runs one round: level choice, guessing loop, and scoring     |
| `generete(level)`   | Returns a random number from `0` to `level - 1`              |
| `Asking()`          | Reads your guess from the keyboard                           |

## Known limitations

- Choosing a level other than 1, 2 or 3 prints `Invalid input`, but the round continues with an undefined range.
- Typing letters instead of numbers is not handled and can make the game loop forever.
- Entering 0 or a negative number of rounds exits the game straight away.

Contributions that fix these are welcome.

## Author

Made by **Mr Ndi** ([@Mr-Ndi](https://github.com/Mr-Ndi)). Enjoy the game! 😄
