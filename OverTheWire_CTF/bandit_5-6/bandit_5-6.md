# Bandit Level 5 → 6

**Platform:** OverTheWire

**Wargame:** Bandit

**Level:** 5 → 6

**Category:** Linux File Enumeration

**Difficulty:** Easy

---

## Challenge Description

The password for the next level is stored in a file somewhere under the `inhere` directory. The target file has the following properties:

- Human-readable
- Exactly **1033 bytes** in size
- Not executable

---

## Initial Enumeration

After logging into the Bandit server, I needed to locate a file matching the challenge requirements.

Instead of manually checking every file, I used the `find` command with multiple filters.

```bash
find . -type f -size 1033c ! -executable
```

Output:

```text
./inhere/maybehere07/.file2
```

The command returned a single file matching all required conditions.

---

## Analysis

This challenge focuses on efficient file enumeration.

Rather than searching directory by directory, `find` allows filtering files based on specific attributes such as:

- File type
- File size
- Permissions
- Ownership
- Name
- Modification time

Combining these filters makes locating a target file much faster, especially in large directory trees.

---

## Solution

Read the discovered file.

```bash
cat ./inhere/maybehere07/.file2
```

The output contains the password for the next Bandit level.

---

## Command Breakdown

### Finding the target file

```bash
find . -type f -size 1033c ! -executable
```

| Option | Description |
|---------|-------------|
| `find` | Search for files and directories |
| `.` | Start searching from the current directory |
| `-type f` | Return only regular files |
| `-size 1033c` | Match files that are exactly **1033 bytes** (`c` = bytes) |
| `!` | Negate the next condition |
| `-executable` | Exclude executable files |

---

## Alternative Approaches

Display the file type before reading it.

```bash
file ./inhere/maybehere07/.file2
```

Or search in multiple steps.

```bash
find . -type f

find . -size 1033c

find . ! -executable
```

Although these methods work, combining all conditions into a single `find` command is more efficient.

---

## Commands Used

```bash
find . -type f -size 1033c ! -executable

cat ./inhere/maybehere07/.file2
```

---

## Why These Commands?

| Command | Purpose |
|---------|---------|
| `find` | Locate files matching multiple conditions |
| `cat` | Display the contents of the target file |

---

## Skills Learned

- Linux Enumeration
- Advanced usage of `find`
- Filtering files by size
- Filtering executable and non-executable files
- Reading hidden files

---

## Tools Used

- SSH
- Linux Terminal
- find
- cat

---

## Notes

The `find` command is one of the most valuable Linux utilities in CTFs and penetration testing.

Some commonly used filters include:

```bash
find . -name "*.txt"

find . -type f

find . -size +10M

find . -user root

find . -perm -4000

find . -mtime -1
```

Learning these options early will significantly speed up Linux enumeration during future CTF challenges and real-world assessments.

---

## Password

```text
Password intentionally omitted.
```