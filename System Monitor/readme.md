# System Monitor

A simple interactive Bash utility that provides a menu for checking basic system information and resource usage.

## Features

* Displays current user
* Shows current working directory
* Displays date and time
* Checks disk usage
* Checks memory usage
* Provides a simple menu interface
* Handles invalid input
* Allows the user to exit cleanly

## How It Works

The script uses a `while` loop to continuously display the menu. User input is stored in a variable and processed using a `case` statement.

Each menu option runs a different Linux command:

| Option | Command   | Purpose           |
| ------ | --------- | ----------------- |
| 1      | `whoami`  | Current user      |
| 2      | `pwd`     | Current directory |
| 3      | `date`    | Current date/time |
| 4      | `df -h`   | Disk usage        |
| 5      | `free -h` | Memory usage      |
| 6      | `break`   | Exit              |

After displaying the result, the script waits for the user to press Enter, clears the terminal, and returns to the menu.

## Bash Concepts Practiced

`while` loops • `case` statements • `read` • variables • `break` • command execution • input handling

## Example

```text
==============================
     System Monitor
==============================

1) Current User
2) Current Directory
3) Current Date
4) Disk Usage
5) Memory Usage
6) Exit

Choose option (1-6): 4

==================
     RESULTS
==================

Filesystem      Size  Used Avail Use%
/dev/sda1       100G   45G   50G  48%
```

## What I Learned

This project helped me practice building a simple menu-driven Bash application while combining user input, loops, `case` statements, and common Linux system commands.
