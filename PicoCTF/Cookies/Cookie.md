# Cookie Monster Secret Recipe

**Platform:** PicoCTF

**Category:** Web Exploitation

**Difficulty:** Easy

## Challenge Description

Find the hidden flag stored inside browser cookies.

## Solution

1. Open the website.
2. Inspect the page.
3. Navigate to **Application → Cookies**.
4. Copy the encoded cookie value.
5. Decode it.

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