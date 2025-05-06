# Custom UNIX Shell

A lightweight UNIX shell implemented in C with support for:

- Command execution
- Piping (`|`)
- Redirection (`>`, `>>`, `<`)
- Command history
- Built-in commands like `cd` and `history`
- Signal handling (e.g., Ctrl+C)
- Sequential (`;`) and conditional (`&&`) execution

---

## Build Instructions

To compile the shell, run:

gcc shell.c command.c execution.c -o my_shell

Then start the shell with:

./my_shell

---

## Features

Supports common shell operations such as:

- Executing basic commands like `ls`, `pwd`, etc.
- Redirecting input/output using `>`, `>>`, `<`
- Piping with `|`
- Command chaining with `;` and `&&`
- Command history using `history`
- Signal handling for `Ctrl+C` (SIGINT)

Use `exit` to quit the shell.

---

## Signal Handling Test

The `sleep_tester_code.c` file demonstrates custom SIGINT behavior.

To compile and run:

gcc sleep_tester_code.c -o sleep_test  
./sleep_test

Press Ctrl+C while it's sleeping to test signal handling.

---

## Example Commands

# --- Basic Command Execution ---
pwd  
ls -l

# --- Redirection Tests ---
echo "Hello World" > test.txt  
cat < test.txt  
echo "Add this line" >> test.txt  
cat test.txt

# --- Piping Tests ---
cat test.txt | grep Hello | wc -l  
ls | sort

# --- Multiple Commands with Semicolon ---
echo First ; echo Second ; ls

# --- Conditional Execution with && ---
mkdir temp && cd temp && touch hello.txt && ls

# --- Command History ---
history

# --- Signal Handling Test ---
sleep 10  
# During sleep, press Ctrl+C to test signal handling

echo Hello > test.txt  
cat < test.txt  
echo World >> test.txt  
cat < test.txt

echo Hello > test.txt; cat test.txt

---

## File List

- `shell.c` — Main loop, signal handling, command parsing  
- `command.c` — Tokenization, command execution, built-in handling  
- `execution.c` — Redirection and pipe handling  
- `shell.h` — Shared headers  
- `sleep_tester_code.c` — Signal handling demo
