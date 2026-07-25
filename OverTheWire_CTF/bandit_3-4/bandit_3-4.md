# Bandit Level 3 → 4

**Platform:** OverTheWire

**Wargame:** Bandit

**Level:** 3 → 4

**Category:** Linux Enumeration

**Difficulty:** Easy

---

## Challenge Description

The password for the next level is stored in a hidden file located inside the `inhere` directory.

---

## Initial Enumeration

After connecting to the remote machine via SSH, I listed the contents of the current directory.

```bash
ls
```

Output:

```text
inhere
```

To enumerate all files, including hidden ones, I used:

```bash
find .
```

Output (relevant):

```text
./inhere
./inhere/...Hiding-From-You
```

The output revealed a hidden file named `...Hiding-From-You`.

---

## Solution

Navigate to the target directory.

```bash
cd inhere
```

Display the contents of the hidden file.

```bash
cat "...Hiding-From-You"
```

The output contains the password for the next Bandit level.

---

## Commands Used

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220

ls

find .

cd inhere

cat "...Hiding-From-You"
```

---

## Why These Commands?

| Command | Purpose |
|---------|---------|
| `ssh` | Connect to the Bandit server |
| `ls` | List files in the current directory |
| `find .` | Enumerate files, including hidden entries |
| `cd` | Change into the target directory |
| `cat` | Read the hidden file |

---

## Skills Learned

- Linux Enumeration
- Hidden Files
- File Discovery using `find`
- Directory Navigation
- Reading Files

---

## Tools Used

- SSH
- Linux Terminal

---

## Password

```text
Password intentionally omitted.
```