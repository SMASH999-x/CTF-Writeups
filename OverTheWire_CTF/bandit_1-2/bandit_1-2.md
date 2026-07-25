# ➖ Bandit Level 1 → 2

**Platform:** OverTheWire
**Category:** Linux File Handling
**Difficulty:** 🟢 Easy

---

## Challenge Description

Retrieve the password stored inside a file literally named `-`.

---

## Approach

A filename of `-` is normally interpreted by command-line tools as a flag or as "read from stdin," not as a real filename. The fix is to force the shell to treat it as a path rather than an option.

---

## Solution

1. List the files in the current directory:

```bash
ls
```

```text
-
```

2. Read the file using a relative path so it isn't mistaken for a flag:

```bash
cat ./-
```

The password is displayed in the output.

---

## Skills Learned

- Handling special/edge-case filenames
- Using relative paths (`./`) to disambiguate arguments

---

## Tools

- Linux Terminal

---

## Password

```text
Password intentionally omitted.
```
