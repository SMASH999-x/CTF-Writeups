# Multi Code

**Platform:** PicoCTF

**Category:** General Skills

**Difficulty:** Easy

## Challenge Description

Decode multiple encoding layers to recover the flag.

## Solution

Decode the message in the following order:

1. Base64
2. Hex
3. ROT13
4. URL Decode

CyberChef can perform all steps.

## Skills Learned

- Base64
- Hex
- ROT13
- URL Encoding
- CyberChef

## Flag

```
picoCTF{nested_enc0ding_ffbbbf57}
```