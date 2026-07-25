# 📖 useless

**Platform:** PicoCTF 2023
**Category:** General Skills
**Difficulty:** 🟡 Medium

## Challenge Description
The challenge provides SSH access to a Linux machine containing a calculator script named `useless`. The objective is to inspect the available resources and retrieve the hidden flag.

## Solution

After connecting to the remote machine, the available files were enumerated:
```bash
find . -type f
```

The script `useless` was found in the user's home directory. Trying the built-in help option only displayed a message:
```bash
./useless -h
./useless --help
```
```text
Read the code first
```

The script source code was inspected. It only implemented four arithmetic operations: `add`, `sub`, `mul`, `div`. No hidden functionality or obvious flag was present in the script.

Searching for additional files or manuals didn't reveal anything useful either:
```bash
find / -name "manual*" 2>/dev/null
```

Since the script hinted at reading documentation, the system manual page was opened:
```bash
man useless
```

The manual described how to use the calculator. At the bottom of the **Authors** section, the flag was embedded directly inside the man page.

## Skills Learned
- Linux file enumeration
- Reading manual pages (`man`)
- Inspecting application documentation
- Basic Linux reconnaissance

## Tools
- SSH
- Linux Terminal
- man

## Flag
```text
picoCTF{hidden}
```
