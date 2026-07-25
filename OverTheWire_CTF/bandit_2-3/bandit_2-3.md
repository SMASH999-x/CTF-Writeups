# 🔤 Bandit Level 2 → 3

**Platform:** OverTheWire
**Category:** Linux File Handling
**Difficulty:** 🟢 Easy

---

## Challenge Description

Retrieve the password stored inside a file whose name contains spaces.

---

## Approach

Spaces in filenames break the shell's normal word-splitting, since each space is treated as a separator between arguments. Quoting the filename keeps it intact as a single argument.

---

## Solution

1. List the available files:

```bash
ls
```

```text
spaces in this filename
```

2. Read the file using quotation marks:

```bash
cat "spaces in this filename"
```

The command prints the password for the next level.

---

## Skills Learned

- Quoting filenames containing whitespace
- Command-line argument handling

---

## Tools

- Linux Terminal

---

## Password

```text
Password intentionally omitted.
```
