# 🔁 Bandit Level 8 → 9

**Platform:** OverTheWire
**Category:** Linux Text Processing
**Difficulty:** 🟢 Easy

---

## Challenge Description

The password for the next level is stored in the file `data.txt` and is the **only line that occurs exactly once**.

---

## Approach

`uniq` can isolate unique lines, but it only compares **adjacent** lines rather than scanning the whole file. Sorting the file first groups all identical lines together, so `uniq -u` can then correctly surface the single line with no duplicates.

---

## Solution

Sort the file, then print only the line that appears exactly once:

```bash
sort data.txt | uniq -u
```

```text
<password>
```

The resulting line is the password for the next level.

---

## Skills Learned

- Using pipelines (`|`) to chain commands
- Sorting text with `sort`
- Identifying unique lines with `uniq -u`

---

## Tools

- SSH
- Linux Terminal
- `sort`
- `uniq`

---

## Password

```text
Password intentionally omitted.
```
