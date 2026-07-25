# Undo

**Platform:** PicoCTF

**Category:** General Skills

**Difficulty:** Easy

## Challenge Description

Reverse a series of Linux text transformations to recover the original flag.

## Connection

```bash
nc foggy-cliff.picoctf.net 54483
```

## Solution

The text was transformed several times.

Commands used:

```bash
base64 -d
rev
tr '-' '_'
```

Reverse each transformation until the original text is recovered.

## Skills Learned

- Base64
- rev
- tr
- Linux Pipes

## Flag

```
picoCTF{Revers1ng_t3xt_Tr4nsf0rm@t10ns_dcc1896c}
```
