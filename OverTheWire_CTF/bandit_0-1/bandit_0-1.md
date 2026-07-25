# 🐧 Bandit Level 0 → 1

**Platform:** OverTheWire
**Category:** Linux Basics
**Difficulty:** 🟢 Easy

---

## Challenge Description

Connect to the Bandit server and retrieve the password stored inside the `readme` file.

---

## Approach

The very first level is about establishing an SSH connection and getting comfortable listing and reading files in a Linux home directory. There's no trick here — just confirm what's in the directory and read it.

---

## Solution

1. Connect to the server over SSH:

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

2. List the files in the current directory:

```bash
ls
```

```text
readme
```

3. Read the file:

```bash
cat readme
```

The output contains the password for the next level.

---

## Skills Learned

- SSH authentication
- Linux file enumeration
- Reading files with `cat`

---

## Tools

- SSH
- Linux Terminal

---

## Password

```text
Password intentionally omitted.
```
