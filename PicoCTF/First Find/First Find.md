# First Find

**Platform:** PicoCTF

**Category:** General Skills

**Difficulty:** Easy

## Challenge Description

Locate the hidden file inside the extracted archive.

## Solution

Extract the archive.

```bash
unzip filename.zip
```

Search for the hidden file.

```bash
find . -name "uber-secret.txt"
```

Open the file to obtain the flag.

## Skills Learned

- unzip
- find
- Linux Filesystem

## Flag

```
picoCTF{f1nd_15_f457_ab443fd1}
```