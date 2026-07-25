# 🕵️ Bandit Level 3 → 4

**Platform:** OverTheWire

**Category:** Linux 

**Difficulty:** 🟢 Easy

---

## Challenge Description

The password for the next level is stored in a hidden file located inside the `inhere` directory.

---

## Approach

`ls` alone doesn't reveal dotfiles (hidden files), so a more thorough enumeration tool is needed. `find` lists every entry in a directory tree regardless of whether it's hidden, making it ideal for this kind of discovery.

---

## Solution

1. List the contents of the current directory:

```bash
ls
```

```text
inhere
```

2. Enumerate all files, including hidden ones:

```bash
find .
```

```text
./inhere
./inhere/...Hiding-From-You
```

3. Navigate into the directory and read the hidden file:

```bash
cd inhere
cat "...Hiding-From-You"
```

The output contains the password for the next level.

---

## Skills Learned

- Discovering hidden files with `find`
- Directory navigation
- Reading files with unusual names

---

## Tools

- SSH
- Linux Terminal

---

## Password

```text
Password intentionally omitted.
```
