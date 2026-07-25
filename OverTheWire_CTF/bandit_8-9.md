# Bandit Level 8 → 9

**Platform:** OverTheWire

**Wargame:** Bandit

**Level:** 8 → 9

**Category:** Linux Text Processing

**Difficulty:** Easy

---

## Challenge Description

The password for the next level is stored in the file `data.txt` and is the **only line that occurs exactly once**.

---

## Initial Enumeration

After logging into the Bandit server, I listed the available files.

```bash
ls
```

Output:

```text
data.txt
```

To understand the file size, I checked its statistics.

```bash
wc data.txt
```

Output (example):

```text
45628 45628 1234567 data.txt
```

The file contains thousands of lines, making manual inspection impractical.

---

## Analysis

The challenge states that the password is the **only unique line** in the file.

The `uniq` command can identify unique lines, but it only works correctly on **adjacent duplicate lines**.

Therefore, the file must first be sorted before using `uniq`.

This is a common Linux text-processing workflow:

```text
sort → uniq
```

---

## Solution

Sort the file, then display only the line that appears exactly once.

```bash
sort data.txt | uniq -u
```

Output:

```text
<password>
```

The resulting line is the password for the next Bandit level.

---

## Command Breakdown

### Sorting the file

```bash
sort data.txt
```

| Option | Description |
|---------|-------------|
| `sort` | Sort lines alphabetically |

---

### Finding unique lines

```bash
uniq -u
```

| Option | Description |
|---------|-------------|
| `uniq` | Filter repeated adjacent lines |
| `-u` | Print only unique lines |

---

### Pipeline

```bash
sort data.txt | uniq -u
```

| Symbol | Description |
|---------|-------------|
| `|` | Send the output of one command as input to another |

---

## Alternative Approaches

Save the sorted output first.

```bash
sort data.txt > sorted.txt

uniq -u sorted.txt
```

Although this works, using a pipeline avoids creating temporary files.

---

## Commands Used

```bash
ls

wc data.txt

sort data.txt | uniq -u
```

---

## Why These Commands?

| Command | Purpose |
|---------|---------|
| `ls` | Verify available files |
| `wc` | Inspect file size |
| `sort` | Arrange duplicate lines together |
| `uniq -u` | Display only the unique line |
| `|` | Connect two commands efficiently |

---

## Skills Learned

- Linux Text Processing
- Using Pipelines
- Sorting Text
- Identifying Unique Data
- Combining Multiple Commands

---

## Tools Used

- SSH
- Linux Terminal
- sort
- uniq

---

## Notes

### Why is `sort` required?

The `uniq` command **does not search the entire file** for duplicates.

It only compares **adjacent lines**.

Example:

```text
apple
banana
apple
```

Running:

```bash
uniq
```

Produces:

```text
apple
banana
apple
```

No duplicates are removed because the matching lines are not adjacent.

After sorting:

```text
apple
apple
banana
```

Now:

```bash
uniq
```

Produces:

```text
apple
banana
```

This is why `sort` is almost always used before `uniq`.

---

### Common `uniq` Options

```bash
uniq -u      # Show only unique lines

uniq -d      # Show duplicated lines

uniq -c      # Count occurrences of each line
```

---

### Pipeline Concept

The pipe operator (`|`) is one of the most powerful features of the Linux shell.

Example:

```bash
cat access.log | grep "POST" | sort | uniq -c | sort -nr
```

This type of command chaining is frequently used in:

- Penetration Testing
- Log Analysis
- SOC Operations
- Incident Response
- Linux Administration

---

## Password

```text
Password intentionally omitted.
```