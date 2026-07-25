# Bandit Level 0 → 1

**Platform:** OverTheWire

**Wargame:** Bandit

**Level:** 0 → 1

**Category:** Linux Basics

**Difficulty:** Easy

---

## Challenge Description

Connect to the Bandit server and retrieve the password stored inside the `readme` file.

---

## Initial Enumeration

Connect to the remote machine using SSH.

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

List the files in the current directory.

```bash
ls
```

Output:

```text
readme
```

---

## Solution

Display the contents of the `readme` file.

```bash
cat readme
```

The output contains the password for the next Bandit level.

---

## Commands Used

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220

ls

cat readme
```

---

## Why These Commands?

| Command | Purpose |
|---------|---------|
| `ssh` | Connect to the remote Bandit server |
| `ls` | List available files |
| `cat` | Read the contents of the file |

---

## Skills Learned

- SSH Authentication
- Linux File Enumeration
- Reading Files using `cat`

---

## Tools Used

- SSH
- Linux Terminal

---

## Password

```text
Password intentionally omitted.
```