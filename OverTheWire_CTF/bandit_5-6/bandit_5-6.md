# 📏 Bandit Level 5 → 6

**Platform:** OverTheWire

**Category:** Linux File Enumeration

**Difficulty:** 🟢 Easy

---

## Challenge Description

The password for the next level is stored in a file somewhere under the `inhere` directory. The target file is human-readable, exactly **1033 bytes**, and **not executable**.

---

## Approach

With a deep, nested directory tree and multiple decoy files, manually checking each one is impractical. `find` supports combining multiple filters — type, size, and permissions — into a single query to pinpoint the exact file.

---

## Solution

Search using all three conditions at once:

```bash
find . -type f -size 1033c ! -executable
```

```text
./inhere/maybehere07/.file2
```

Read the discovered file:

```bash
cat ./inhere/maybehere07/.file2
```

The output contains the password for the next level.

---

## Skills Learned

- Advanced usage of `find`
- Filtering files by size and permissions
- Combining multiple search conditions efficiently

---

## Tools

- SSH
- Linux Terminal
- `find`
- `cat`

---

## Password

```text
Password intentionally omitted.
```
