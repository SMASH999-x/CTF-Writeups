# 🍪 Cookie Monster Secret Recipe

**Platform:** PicoCTF
**Category:** Web Exploitation
**Difficulty:** 🟢 Easy

## Challenge Description
Find the hidden flag stored inside browser cookies.

## Approach
Browser cookies frequently hold session data or, in intentionally vulnerable apps, flags encoded in a reversible format. DevTools is the fastest way to inspect them without any external tooling.

## Solution
1. Open the website.
2. Open **DevTools** (`F12` or right-click → *Inspect*).
3. Navigate to **Application → Cookies**.
4. Copy the encoded cookie value.
5. Decode it locally:

```bash
echo "encoded_text" | base64 --decode
```

The decoded output contains the flag.

## Skills Learned
- Browser DevTools
- Cookies
- Base64
- Web Enumeration

## Tools
- Browser
- Linux Terminal

## Flag
```text
picoCTF{hidden}
```
