# Bandit Level 10 → 11

**Platform:** OverTheWire  

**Category:** Linux / Encoding  

**Difficulty:** 🟢 Easy

---

## Challenge Description

The password for the next level is stored in `data.txt`, which contains Base64-encoded data.

---

## Solution

After connecting to the Bandit server, I listed the available files and found `data.txt`.

Since the challenge stated that the file was Base64 encoded, I decoded its contents using the `base64` utility with the `--decode` option, revealing the password for the next level.

```bash
cat data.txt | base64 --decode
```

---

## Commands Used

| Command | Purpose |
|---------|---------|
| `ls` | List files in the current directory |
| `cat data.txt` | Display the file contents |
| `base64 --decode` | Decode Base64-encoded data |

---

## Why This Works

Base64 is an encoding scheme used to represent binary data as printable text. Decoding the file restores the original plaintext, which contains the password.

---

## Skills Learned

- Base64 encoding and decoding
- Working with Linux pipelines
- Reading encoded files from the terminal

---

## Tools Used

- SSH
- Linux Terminal
- `base64`

---

## Password

```text
Password intentionally omitted.
```