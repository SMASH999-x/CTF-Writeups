# 💉 ping-cmd

**Platform:** PicoCTF

**Category:** General Skills

**Difficulty:** 🟢 Easy

## Challenge Description
The application only accepts the IP address `8.8.8.8` for the `ping` command. The goal is to retrieve the flag by finding a way to execute an additional command.

## Approach
The input field is passed unsanitized into a shell command. Chaining a second command with `;` lets it execute alongside the intended `ping`.

## Connection
```bash
nc mysterious-sea.picoctf.net 53525
```

## Solution
The input was vulnerable to **command injection**. After entering the allowed IP address, another command was appended using `;`.

### Payload
```text
8.8.8.8; cat flag.txt
```

The server first executed the `ping` command and then executed `cat flag.txt`, which revealed the flag.

## Skills Learned
- Command Injection
- Linux Commands
- Netcat (`nc`)
- Input Validation

## Tools
- Linux Terminal
- Netcat

## Flag
```text
picoCTF{hidden}
```
