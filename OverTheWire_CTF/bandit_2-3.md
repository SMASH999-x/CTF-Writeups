# Bandit Level 2 → 3

**Platform:** OverTheWire

**Wargame:** Bandit

**Level:** 2 → 3

**Category:** Linux File Handling

**Difficulty:** Easy

---

## Challenge Description

Retrieve the password stored inside a file whose name contains spaces.

---

## Initial Enumeration

List the available files.

```bash
ls
```

Output:

```text
spaces in this filename
```

The filename contains spaces, so it cannot be referenced normally.

---

## Solution

Read the file using quotation marks.

```bash
cat "spaces in this filename"
```

The command prints the password for the next level.

---

## Commands Used

```bash
ls

cat "spaces in this filename"
```

---

## Why These Commands?

| Command | Purpose |
|---------|---------|
| `ls` | Identify available files |
| `cat` | Read the target file |
| Quotes | Handle filenames containing spaces |

---

## Skills Learned

- Quoting Filenames
- Linux File Handling
- Command-Line Basics

---

## Tools Used

- Linux Terminal

---

## Password

```text
Password intentionally omitted.
```