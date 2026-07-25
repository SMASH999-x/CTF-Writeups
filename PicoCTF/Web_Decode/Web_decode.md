# 🌐 WebDecode

**Platform:** PicoCTF
**Category:** General Skills
**Difficulty:** 🟢 Easy

## Challenge Description
Recover the encoded flag from the target website.

## Solution
1. Open the challenge website.
2. Inspect the page source (`Ctrl+U`).
3. Locate the encoded text embedded in the HTML.
4. Decode it:
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
picoCTF{hidden}
```
