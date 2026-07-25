# 🧩 Piece by Piece

**Platform:** PicoCTF
**Category:** General Skills
**Difficulty:** 🟢 Easy

## Challenge Description
Combine multiple file parts and extract the archive to reveal the flag.

## Connection
```bash
ssh ctf-player@dolphin-cove.picoctf.net -p PORT
```

## Solution
Merge the split archive parts in order:
```bash
cat parts_* > combined.zip
```

Extract the combined archive:
```bash
unzip combined.zip
```

Enter the provided password when prompted. The extracted file contains the flag.

## Skills Learned
- cat
- ZIP Archives
- Linux Files

## Flag
```text
picoCTF{hidden}
```
