# User Directory Generator

A simple Bash script that creates an organized directory structure for an employee based on their name and department.

## Features

* Accepts an employee name
* Allows the user to select a department
* Creates an employee directory
* Automatically creates folders for:

  * Documents
  * Reports
  * Logs
  * Downloads
* Displays the employee and department information after creation

## How It Works

The script first asks for the employee's name and department.

A `case` statement converts the department selection into a department name:

```bash
case $deptchoice in
    1) dept="IT" ;;
    2) dept="HR" ;;
    3) dept="SALES" ;;
    4) dept="MARKETING" ;;
    5) dept="ACCOUNTING" ;;
esac
```

It then uses `mkdir` to create the employee's directory structure:

```text
Employee/
└── UserFiles/
    ├── Documents/
    ├── Reports/
    ├── Logs/
    └── Downloads/
```

If an invalid department is selected, the script displays an error and exits.

## Bash Concepts Practiced

`read` • variables • `case` statements • `mkdir` • directory organization • input handling • exit codes

## Example

```text
Enter employee name: John

Choose a department:
1) IT
2) HR
3) SALES
4) MARKETING
5) ACCOUNTING

Enter choice (1-5): 1

Generating directories...

==============================
 Directory Created Successfully
==============================
Employee : John
Department : IT

Folders Created:
- Documents
- Reports
- Logs
- Downloads
```

## What I Learned

This project helped me practice using Bash to automate repetitive filesystem tasks. Instead of manually creating multiple folders for each employee, the script generates the directory structure automatically from a few user inputs.
