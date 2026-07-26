# 🔐 Multi Code

**Platform:** PicoCTF

**Category:** General Skills

**Difficulty:** 🟢 Easy

## Challenge Description
Decode multiple encoding layers to recover the flag.

## Solution
The message was layered through four transformations, decoded in this order:

1. **Base64** decode
2. **Hex** decode
3. **ROT13** decode
4. **URL** decode

[CyberChef](https://gchq.github.io/CyberChef/) can perform the entire chain in a single recipe — stack the operations in the order above and bake.

## Skills Learned
- Base64
- Hex
- ROT13
- URL Encoding
- CyberChef

## Flag
```text
picoCTF{hidden}
```
