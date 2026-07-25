# Bandit Level 4 → 5

**Platform:** OverTheWire

**Wargame:** Bandit

**Level:** 4 → 5

**Category:** Linux File Inspection

**Difficulty:** Easy

---

## Challenge Description

The password for the next level is stored in the **only human-readable file** inside the `inhere` directory.

---

## Initial Enumeration

After connecting to the Bandit server, I enumerated the current directory.

```bash
find .
```

Output (relevant):

```text
./inhere
./inhere/-file00
./inhere/-file01
./inhere/-file02
./inhere/-file03
./inhere/-file04
./inhere/-file05
./inhere/-file06
./inhere/-file07
./inhere/-file08
./inhere/-file09
```

The `inhere` directory contains multiple files with similar names.

---

## Investigation

I attempted to inspect the files using `cat`.

```bash
cat inhere/-file00
cat inhere/-file01
cat inhere/-file03
cat inhere/-file06
cat inhere/-file08
cat inhere/-file09
```

Most files displayed unreadable binary data.

When reading `-file07`, the output was human-readable text containing the password for the next level.

```bash
cat inhere/-file07
```

---

## Solution

Read the human-readable file.

```bash
cat inhere/-file07
```

The output contains the password for **Bandit Level 5**.

> **Note:** A more efficient approach is to identify the readable file using the `file` command:

```bash
file inhere/*
```

This command identifies which file contains ASCII text without manually opening every file.

---

## Commands Used

```bash
find .

cat inhere/-file00

cat inhere/-file01

cat inhere/-file03

cat inhere/-file06

cat inhere/-file07

cat inhere/-file08

cat inhere/-file09
```

---

## Why These Commands?

| Command | Purpose |
|---------|---------|
| `find .` | Enumerate the directory structure |
| `cat` | Inspect file contents |
| `file` *(alternative)* | Determine file types and identify the readable file |

---

## Skills Learned

- Linux Enumeration
- Inspecting File Contents
- Distinguishing Text Files from Binary Files
- Using `file` to identify file types

---

## Tools Used

- SSH
- Linux Terminal

---

## Password

```text
Password intentionally omitted.
```