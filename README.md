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
File List

- shell.c — Main loop, signal handling, command parsing

- command.c — Tokenization, command execution, built-in handling

- execution.c — Redirection and pipe handling

- shell.h — Shared headers

- sleep_tester_code.c — Signal handling demo

---

## Build Instructions

To compile the shell, run:

```bash
gcc shell.c command.c execution.c -o my_shell

./my_shell

// Examples of supported usage:

ls -l
cd ..
echo Hello > file.txt
cat < file.txt | grep Hello
history

// Signal Handling Test
// The included sleep_tester_code.c demonstrates custom handling of SIGINT (Ctrl+C):

gcc sleep_tester_code.c -o sleep_test
./sleep_test

