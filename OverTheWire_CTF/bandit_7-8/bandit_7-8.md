# Bandit Level 7 → 8

**Platform:** OverTheWire

**Wargame:** Bandit

**Level:** 7 → 8

**Category:** Linux Text Processing

**Difficulty:** Easy

---

## Challenge Description

The password for the next level is stored in the file `data.txt` next to the word **millionth**.

---

## Initial Enumeration

After connecting to the Bandit server, I listed the files in the current directory.

```bash
ls
```

Output:

```text
data.txt
```

To understand the size of the file, I checked its statistics.

```bash
wc data.txt
```

Output:

```text
98567 197133 4184396 data.txt
```

The output indicates that the file contains:

- **98,567 lines**
- **197,133 words**
- **4,184,396 bytes**

Since manually searching such a large file would be inefficient, a text-search utility is required.

---

## Analysis

The challenge hint states that the password is located **next to the word `millionth`**.

Searching manually with `cat` would require inspecting thousands of lines.

A better approach is to use `grep`, which searches text for matching patterns and prints only the relevant lines.

---

## Solution

Search the file for the keyword.

```bash
grep "millionth" data.txt
```

Output:

```text
millionth       <password>
```

The value displayed after `millionth` is the password for the next Bandit level.

---

## Command Breakdown

### Counting file statistics

```bash
wc data.txt
```

| Option | Description |
|---------|-------------|
| `wc` | Count lines, words, and bytes in a file |

Output format:

```text
Lines  Words  Bytes  Filename
```

---

### Searching for text

```bash
grep "millionth" data.txt
```

| Option | Description |
|---------|-------------|
| `grep` | Search for matching text |
| `"millionth"` | Search pattern |
| `data.txt` | Target file |

---

## Alternative Approaches

Using a pipeline:

```bash
cat data.txt | grep "millionth"
```

Although this works, it is unnecessary because `grep` can read files directly.

A shorter and more efficient solution is:

```bash
grep "millionth" data.txt
```

---

## Commands Used

```bash
ls

wc data.txt

grep "millionth" data.txt
```

---

## Why These Commands?

| Command | Purpose |
|---------|---------|
| `ls` | Verify available files |
| `wc` | Inspect file size and statistics |
| `grep` | Search for the required keyword efficiently |

---

## Skills Learned

- Linux Text Processing
- Searching with `grep`
- Reading file statistics using `wc`
- Efficient handling of large text files

---

## Tools Used

- SSH
- Linux Terminal
- grep
- wc

---

## Notes

### Why use `grep`?

`grep` is one of the most frequently used commands in Linux, CTFs, and penetration testing. It allows you to quickly search through files, logs, and command output.

Common examples:

```bash
grep "root" /etc/passwd

grep -i password file.txt

grep -r "admin" .

grep -n "error" logfile.log

history | grep ssh
```

Useful options:

| Option | Purpose |
|---------|---------|
| `-i` | Ignore case |
| `-n` | Show line numbers |
| `-r` | Search recursively |
| `-v` | Show non-matching lines |
| `-c` | Count matching lines |

> **Best Practice:** Avoid unnecessary pipelines like `cat file | grep pattern` when `grep pattern file` achieves the same result more efficiently.

---

## Password

```text
Password intentionally omitted.
```