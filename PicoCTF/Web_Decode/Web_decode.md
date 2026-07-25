# WebDecode

**Platform:** PicoCTF

**Category:** General Skills

**Difficulty:** Easy

## Challenge Description

Recover the encoded flag from the target website.

## Solution

1. Open the challenge website.
2. Inspect the page source.
3. Locate the encoded text.
4. Decode it using:

```bash
echo "encoded_text" | base64 --decode
```

5. The decoded output contains the flag.

## Skills Learned

- HTML Source Inspection
- Base64 Decoding
- Linux Terminal

## Tools

- Browser
- Linux Terminal

## Flag

```text
Hidden
```