# Bandit Level 11 → 12

**Platform:** OverTheWire  

**Category:** Linux / Cryptography  

**Difficulty:** 🟢 Easy

---

## Challenge Description

The password for the next level is stored in `data.txt`, where all lowercase (`a-z`) and uppercase (`A-Z`) letters have been rotated by 13 positions (ROT13).

---

## Solution

After connecting to the Bandit server, I inspected the contents of `data.txt`.

```bash
cat data.txt
```

The text was encoded using **ROT13**, a Caesar cipher that rotates each alphabetical character by 13 positions.

To decode it, I used the `tr` command to translate both uppercase and lowercase letters back to their original values.

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

The decoded output revealed the password for the next level.

---

## Commands Used

| Command | Purpose |
|---------|---------|
| `ls` | List files in the current directory |
| `cat data.txt` | Display the encoded content |
| `tr 'A-Za-z' 'N-ZA-Mn-za-m'` | Decode ROT13 by translating alphabet characters |

---

## Why This Works

ROT13 shifts every letter by 13 positions in the alphabet. Since the alphabet contains 26 letters, applying the same transformation again restores the original text.

---

## Skills Learned

- Understanding ROT13 encoding
- Using the `tr` command for character translation
- Decoding simple substitution ciphers in Linux

---

## Tools Used

- SSH
- Linux Terminal
- `tr`

---

## Password

```text
Password intentionally omitted.
```