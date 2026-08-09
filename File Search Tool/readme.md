# File Search Tool

A simple Bash script that searches the user's home directory for a file based on a filename entered by the user.

## Project Overview

The **File Search Tool** is a command-line utility written in Bash. It accepts a filename from the user, validates the input, searches the home directory using the `find` command, and displays the location of any matching file.

The project demonstrates basic Bash scripting concepts such as:

* User input with `read`
* Input validation
* `while` loops
* Conditional statements
* Command substitution
* The `find` command
* Redirecting error output
* Variables
* Basic command-line output formatting

## How It Works

The script follows this general process:

1. Display the program title.
2. Ask the user to enter a filename.
3. Check whether the input is empty.
4. Continue asking until a filename is provided.
5. Search the home directory for a matching file.
6. Display the result.
7. Notify the user that the search is complete.

### 1. Display the Program Header

```bash
echo "=============================="
echo "       File Search Tool"
echo "=============================="
```

These `echo` commands create a simple interface for the script.

---

### 2. Ask for a Filename

```bash
while true
do
    read -p "Enter filename (ex. report.txt): " filename
```

The script uses `read` to get input from the user and stores it in the `filename` variable.

The `while true` loop allows the script to repeatedly ask for input until valid input is provided.

---

### 3. Validate the Input

```bash
if [ -z "$filename" ]; then
    echo "Filename cannot be empty. Please try again."
else
    break
fi
```

The `-z` test checks whether the value of `$filename` has zero characters.

If the user presses Enter without entering anything, the script displays an error message and asks again.

If a filename is entered, `break` exits the loop.

**Concept demonstrated:** input validation.

---

### 4. Search the Home Directory

```bash
result=$(find ~ -name "*$filename.*" 2>/dev/null)
```

This is the main part of the script.

The `find` command searches through the user's home directory:

```bash
find ~
```

The `-name` option tells `find` to search for names matching a specific pattern.

The pattern:

```bash
"*$filename.*"
```

uses wildcards to match filenames containing the entered filename followed by an extension.

For example, if the user enters:

```text
report
```

the pattern can match files such as:

```text
report.txt
report.pdf
old-report.doc
```

The search result is stored in the `result` variable using **command substitution**:

```bash
$(...)
```

The following redirects error messages to `/dev/null`:

```bash
2>/dev/null
```

This prevents permission-related errors from cluttering the output.

---

### 5. Check Whether a File Was Found

```bash
if [ -z "$result" ]; then
```

The script checks whether the `result` variable is empty.

If it is empty, no matching file was found.

```bash
echo "      FILE NOT FOUND"
echo "No file named '$filename' was found."
```

If a result exists, the script displays the location:

```bash
echo "       FILE FOUND!"
echo "Location:"
echo "$result"
```

---

## Example Run

### File Found

```text
==============================
       File Search Tool
==============================

Enter filename (ex. report.txt): report

Searching...

==============================
       FILE FOUND!
==============================
Location:
/home/user/Documents/report.txt

Search Complete.
```

### File Not Found

```text
==============================
       File Search Tool
==============================

Enter filename (ex. report.txt): invoice

Searching...

==============================
      FILE NOT FOUND
==============================
No file named 'invoice' was found.

Search Complete.
```

### Empty Input

```text
Enter filename (ex. report.txt):
Filename cannot be empty. Please try again.

Enter filename (ex. report.txt):
```

The script continues asking until the user provides a filename.

## Key Bash Concepts Demonstrated

| Concept       | Purpose                               |
| ------------- | ------------------------------------- |
| `read`        | Accept user input                     |
| Variables     | Store the filename and search results |
| `while`       | Repeat input until valid              |
| `if`          | Make decisions based on conditions    |
| `-z`          | Check whether a variable is empty     |
| `break`       | Exit the input loop                   |
| `find`        | Search the filesystem                 |
| `$(...)`      | Capture command output                |
| `2>/dev/null` | Suppress error messages               |
| `echo`        | Display information to the user       |

## Limitations

This is intentionally a simple version of a file-search utility.

Current limitations include:

* The search is limited to the user's home directory.
* The filename matching uses a pattern rather than an exact filename match.
* The script does not provide advanced search filters such as file type, size, or modification date.
* Multiple matching files are displayed together if they are found.

## What I Learned

This project helped reinforce the basics of Bash scripting by combining user input, loops, conditional logic, variables, command substitution, and Linux filesystem commands into one practical utility.

Rather than simply running `find` manually, the script provides a small interactive interface that makes the search process easier for the user.
