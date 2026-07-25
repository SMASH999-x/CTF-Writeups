# 🕷️ Intro to Burp

**Platform:** PicoCTF
**Category:** Web Exploitation
**Difficulty:** 🟢 Easy

## Challenge Description
Bypass OTP verification using Burp Suite.

## Approach
The application trusts client-supplied verification parameters. By intercepting the request that submits the OTP and stripping the parameter entirely, the server-side check can be short-circuited.

## Solution
1. Open the website and configure the browser to proxy through **Burp Suite**.
2. Register a new account normally.
3. Intercept the OTP verification request in **Proxy**.
4. Send the request to **Repeater**.
5. Remove the `otp` parameter from the request.
6. Forward the modified request.

The response returns the flag.

## Skills Learned
- Burp Suite
- HTTP Requests
- Parameter Manipulation

## Tools
- Burp Suite

## Flag
```text
picoCTF{hidden}
```
