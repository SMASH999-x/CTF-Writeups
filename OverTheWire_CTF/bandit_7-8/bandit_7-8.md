# 🔎 Bandit Level 7 → 8

**Platform:** OverTheWire
**Category:** Linux Text Processing
**Difficulty:** 🟢 Easy

---

## Challenge Description

The password for the next level is stored in the file `data.txt` next to the word **millionth**.

---

## Approach

The file is large (roughly 98,000 lines and 4 MB), so manually scrolling through it with `cat` isn't realistic. `grep` searches for a matching pattern and prints only the relevant line, making it the right tool for pinpointing a single keyword in a huge file.

---

## Solution

1. Check the file's scale first:

```bash
wc data.txt
```

```text
98567 197133 4184396 data.txt
```

2. Search directly for the keyword:

```bash
grep "millionth" data.txt
```

```text
millionth       <password>
```

The value after `millionth` is the password for the next level.

---

## Skills Learned

- Fast text search with `grep`
- Inspecting file statistics with `wc`
- Avoiding unnecessary pipelines (`grep file` vs. `cat file | grep`)

---

## Tools

- SSH
- Linux Terminal
- `grep`
- `wc`

---

## Password

```text
Password intentionally omitted.
```
