# 🗂️ First Find

**Platform:** PicoCTF
**Category:** General Skills
**Difficulty:** 🟢 Easy

## Challenge Description
Locate the hidden file inside the extracted archive.

## Solution
Extract the archive:
```bash
unzip filename.zip
```

Search recursively for the hidden file:
```bash
find . -name "uber-secret.txt"
```

Open the file to obtain the flag.

## Skills Learned
- unzip
- find
- Linux Filesystem

## Flag
```text
picoCTF{hidden}
```
