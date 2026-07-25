# Piece by Piece

**Platform:** PicoCTF

**Category:** General Skills

**Difficulty:** Easy

## Challenge Description

Combine multiple file parts and extract the archive to reveal the flag.

## Connection

```bash
ssh ctf-player@dolphin-cove.picoctf.net -p PORT
```

## Solution

Merge the split archive.

```bash
cat parts_* > combined.zip
```

Extract it.

```bash
unzip combined.zip
```

Enter the provided password.

The extracted file contains the flag.

## Skills Learned

- cat
- ZIP Archives
- Linux Files

## Flag

```
picoCTF{z1p_and_spl1t_f1l3s_4r3_fun_78b76e61}
```