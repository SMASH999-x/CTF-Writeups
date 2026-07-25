# 📄 Bandit Level 4 → 5

**Platform:** OverTheWire

**Category:** Linux File Inspection

**Difficulty:** 🟢 Easy

---

## Challenge Description

The password for the next level is stored in the **only human-readable file** inside the `inhere` directory.

---

## Approach

The `inhere` directory contains multiple similarly-named files, most of which hold binary/garbage data. Rather than eyeballing every file with `cat`, the `file` command can classify each one by content type in a single pass.

---

## Solution

1. Enumerate the directory:

```bash
find .
```

```text
./inhere/-file00
./inhere/-file01
...
./inhere/-file09
```

2. Identify which file contains ASCII text without opening every file manually:

```bash
file inhere/*
```

3. Read the human-readable file:

```bash
cat inhere/-file07
```

The output contains the password for the next level.

---

## Skills Learned

- Distinguishing text files from binary files
- Using `file` to identify file types efficiently

---

## Tools

- SSH
- Linux Terminal

---

## Password

```text
Password intentionally omitted.
```
