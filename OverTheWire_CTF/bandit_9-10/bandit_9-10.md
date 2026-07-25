# Bandit Level 9 → 10

**Platform:** OverTheWire

**Wargame:** Bandit

**Level:** 9 → 10

**Category:** Linux Binary Analysis

**Difficulty:** Easy

---

## Challenge Description

The password for the next level is stored in the file `data.txt` among many non-human-readable characters. It is preceded by several `=` characters.

---

## Initial Enumeration

After connecting to the Bandit server, I verified the available files.

```bash
ls
```

Output:

```text
data.txt
```

Since the challenge mentions non-human-readable characters, opening the file directly with `cat` would produce unreadable output.

Instead, I extracted only printable strings from the file.

```bash
strings data.txt
```

The output contained hundreds of readable strings.

Among them, the following lines were particularly interesting:

```text
========== password
========== is
========== B0s2khmbT9u0geKuOoVGW3JZKhndE3BG
```

---

## Analysis

This challenge introduces one of the most useful Linux utilities for binary analysis: `strings`.

Binary files often contain embedded text such as:

- Passwords
- URLs
- File paths
- Error messages
- Usernames
- Configuration values

The `strings` command extracts printable ASCII sequences while ignoring binary data, making it much easier to inspect unknown files.

The challenge hint states that the password is preceded by several `=` characters, so the output was inspected until the matching string was found.

---

## Solution

Extract printable strings from the binary file.

```bash
strings data.txt
```

Locate the line following the repeated `=` characters.

```text
========== B0s2khmbT9u0geKuOoVGW3JZKhndE3BG
```

The text after the equal signs is the password for the next Bandit level.

---

## Command Breakdown

### Extract printable strings

```bash
strings data.txt
```

| Option | Description |
|---------|-------------|
| `strings` | Extract printable text from binary files |
| `data.txt` | Target file |

---

## Alternative Approaches

Filter the output using `grep`.

```bash
strings data.txt | grep "==="
```

Or search specifically for the word `password`.

```bash
strings data.txt | grep password -A 2
```

Both methods reduce the amount of output and make locating the password faster.

---

## Commands Used

```bash
ls

strings data.txt
```

---

## Why These Commands?

| Command | Purpose |
|---------|---------|
| `ls` | Verify available files |
| `strings` | Extract readable text from binary data |

---

## Skills Learned

- Binary File Inspection
- Extracting Printable Strings
- Basic Digital Forensics
- Linux Text Processing
- Command-Line Analysis

---

## Tools Used

- SSH
- Linux Terminal
- strings

---

## Notes

### What is `strings`?

`strings` scans a binary file and prints sequences of printable characters.

It is widely used in:

- Reverse Engineering
- Malware Analysis
- Digital Forensics
- Capture The Flag (CTF) challenges
- Incident Response

---

### Common Examples

Extract readable text:

```bash
strings program
```

Search for URLs:

```bash
strings malware.exe | grep http
```

Find passwords or secrets:

```bash
strings memory.dump | grep -i password
```

Search for API keys:

```bash
strings binary | grep KEY
```

---

### Why not use `cat`?

Binary files contain non-printable bytes that make the terminal output unreadable.

`strings` filters out the binary data and displays only meaningful text, making analysis significantly easier.

---

### Real-World Use Cases

Security professionals frequently use `strings` to:

- Discover hardcoded credentials
- Identify API endpoints
- Find hidden configuration values
- Recover debugging information
- Inspect suspicious binaries before deeper analysis

It is often one of the first commands executed when analyzing an unknown executable.

---

## Password

```text
Password intentionally omitted.
```