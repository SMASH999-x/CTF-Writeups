# Bandit Level 12 → 13

**Platform:** OverTheWire  

**Category:** Linux / File Analysis

**Difficulty:** 🔵 Medium

---

## Challenge Description

The password for the next level is stored in `data.txt`, which is a hexdump of a file that has been compressed multiple times. The original file must be reconstructed and repeatedly identified and extracted until the password is revealed.

---

## Solution

The challenge starts with a hexadecimal dump instead of a normal file. The first step is to recreate the original binary using `xxd`.

```bash
xxd -r data.txt > data
```

The resulting file was identified with the `file` command to determine its format.

```bash
file data
```

The file turned out to be compressed several times using different formats (gzip, bzip2, and tar archives). After each extraction, the new file type was checked again with `file` until the final plaintext file containing the password was reached.

---

## Commands Used

| Command | Purpose |
|---------|---------|
| `mktemp -d` | Create a temporary working directory |
| `cp` | Copy the challenge file into the workspace |
| `cd` | Change to the working directory |
| `xxd -r` | Convert a hex dump back into a binary file |
| `file` | Identify the current file format |
| `mv` | Rename files with the correct extension |
| `gzip -d` | Extract Gzip-compressed files |
| `bzip2 -d` | Extract Bzip2-compressed files |
| `tar -xf` | Extract TAR archives |
| `cat` | Display the final password |

---

## Why This Works

The challenge chains multiple compression formats together. Since the extension is removed after each layer, the `file` command is required to identify the current format before selecting the appropriate extraction tool. Repeating this process eventually reveals the original plaintext.

---

## Skills Learned

- Working with hexadecimal dumps using `xxd`
- Identifying file formats with `file`
- Using temporary working directories
- Extracting nested compressed files
- Handling Gzip, Bzip2, and TAR archives in Linux

---

## Tools Used

- SSH
- Linux Terminal
- `xxd`
- `file`
- `gzip`
- `bzip2`
- `tar`

---

## Password

```text
Password intentionally omitted.
```