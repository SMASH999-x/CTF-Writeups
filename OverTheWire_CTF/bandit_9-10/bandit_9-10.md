# 🧬 Bandit Level 9 → 10

**Platform:** OverTheWire
**Category:** Linux Binary Analysis
**Difficulty:** 🟢 Easy

---

## Challenge Description

The password for the next level is stored in the file `data.txt` among many non-human-readable characters, preceded by several `=` characters.

---

## Approach

`data.txt` contains a mix of binary and printable data, so opening it directly with `cat` produces unreadable output. `strings` extracts only the printable ASCII sequences from a file, which is the standard first step when inspecting unknown or binary content.

---

## Solution

Extract printable strings and filter down to the marker mentioned in the hint:

```bash
strings data.txt | grep -A 2 "==="
```

```text
========== password
========== is
========== <password>
```

The text following the equal signs is the password for the next level.

---

## Skills Learned

- Extracting printable text from binary data with `strings`
- Basic digital forensics / binary inspection
- Filtering large `strings` output with `grep`

---

## Tools

- SSH
- Linux Terminal
- `strings`

---

## Password

```text
Password intentionally omitted.
```
