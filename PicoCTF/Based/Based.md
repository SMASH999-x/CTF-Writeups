# 🔢 PicoCTF — Based

**Platform:** PicoCTF

**Category:** General Skills

**Difficulty:** 🟡 Medium

---

## Challenge Description

Connect to a remote service that presents a series of values encoded in different numeral systems (Binary, Octal, and Hexadecimal). Each value must be decoded to its ASCII equivalent and submitted correctly, in order, within the session's time limit to receive the flag.

---

## Approach

The service is a simple encode/decode gate: it sends a value in one of three common representations and expects the decoded ASCII word back before it will move to the next stage. Solving it comes down to recognizing which base each value is in and converting it correctly and quickly, since the session is time-limited.

---

## Solution

**1. Connect to the service:**

```bash
nc fickle-tempest.picoctf.net 61385
```

**2. Decode each stage as it appears:**

| Stage | Encoding | Challenge | Decoded |
|-------|----------|-----------|---------|
| 1 | Binary | `01110011 01110100 01110010 01100101 01100101 01110100` | `street` |
| 2 | Octal | `0143 0157 0155 0160 0165 0164 0145 0162` | `computer` |
| 3 | Hex | `636f6d7075746572` | `computer` |

**3. Submit each decoded word back to the service.** Once all stages pass, the flag is returned.

**Quick conversion commands used for verification:**

```bash
# Hex
echo 636f6d7075746572 | xxd -r -p

# Binary
echo "01110011" | perl -lape '$_=chr oct("0b$_")'

# Octal
printf "\143\157\155\160\165\164\145\162\n"
```

---

## Skills Learned

- Binary, octal, and hexadecimal → ASCII conversion
- Rapid manual decoding under time pressure
- Scripted decoding with `xxd`, `perl`, and `printf`
- Netcat-based interaction with remote CTF services

---

## Tools

- Netcat (`nc`)
- Linux Terminal
- `xxd`, `perl`, `printf`

---

## Flag

```text
Flag intentionally omitted.
```