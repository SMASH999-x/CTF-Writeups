# Bandit Level 1 → 2

**Platform:** OverTheWire

**Wargame:** Bandit

**Level:** 1 → 2

**Category:** Linux File Handling

**Difficulty:** Easy

---

## Challenge Description

Retrieve the password stored inside a file named `-`.

---

## Initial Enumeration

List the files in the current directory.

```bash
ls
```

Output:

```text
-
```

The filename begins with a dash, which is normally interpreted as a command option.

---

## Solution

Specify the file using a relative path.

```bash
cat ./-
```

The password is displayed.

---

## Commands Used

```bash
ls

cat ./-
```

---

## Why These Commands?

| Command | Purpose |
|---------|---------|
| `ls` | Identify available files |
| `cat ./-` | Read a filename beginning with `-` |

---

## Skills Learned

- Handling Special Filenames
- Relative Paths
- Linux File Reading

---

## Tools Used

- Linux Terminal

---

## Password

```text
Password intentionally omitted.
```