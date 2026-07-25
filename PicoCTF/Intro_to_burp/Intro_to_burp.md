# Intro to Burp

**Platform:** PicoCTF

**Category:** Web Exploitation

**Difficulty:** Easy

## Challenge Description

Bypass OTP verification using Burp Suite.

## Solution

1. Open the website.
2. Configure Burp Suite.
3. Register normally.
4. Intercept the OTP request.
5. Send it to Repeater.
6. Remove the OTP parameter.
7. Forward the modified request.

The response returns the flag.

## Skills Learned

- Burp Suite
- HTTP Requests
- Parameter Manipulation

## Tools

- Burp Suite

## Flag

```text
Hidden
```