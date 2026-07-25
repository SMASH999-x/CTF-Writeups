# Bandit Level 6 → 7

**Platform:** OverTheWire

**Wargame:** Bandit

**Level:** 6 → 7

**Category:** Linux File Enumeration

**Difficulty:** Medium

---

## Challenge Description

The password for the next level is stored **somewhere on the server** and has the following properties:

- Owned by **user `bandit7`**
- Owned by **group `bandit6`**
- Exactly **33 bytes** in size

---

## Initial Enumeration

Unlike previous levels, the target file is not located inside the current directory.

To search the entire filesystem efficiently, I used the `find` command with filters matching the challenge requirements.

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

Output:

```text
/var/lib/dpkg/info/bandit7.password
```

The command returned a single file matching all required conditions.

---

## Analysis

This challenge demonstrates how powerful the `find` command can be when multiple search conditions are combined.

Searching manually would be impractical because the file could be located anywhere on the system.

Many directories on Linux are inaccessible to regular users, which generates numerous permission errors. To keep the output clean, standard error was redirected to `/dev/null`.

---

## Solution

Read the discovered file.

```bash
cat /var/lib/dpkg/info/bandit7.password
```

The output contains the password for the next Bandit level.

---

## Command Breakdown

### Searching the filesystem

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

| Option | Description |
|---------|-------------|
| `find` | Search for files and directories |
| `/` | Start searching from the filesystem root |
| `-user bandit7` | Files owned by user `bandit7` |
| `-group bandit6` | Files belonging to group `bandit6` |
| `-size 33c` | Files exactly **33 bytes** (`c` = bytes) |
| `2>` | Redirect standard error |
| `/dev/null` | Discard permission denied messages |

---

## Alternative Approaches

Search step by step.

```bash
find / -user bandit7 2>/dev/null

find / -group bandit6 2>/dev/null

find / -size 33c 2>/dev/null
```

Although this works, combining all conditions into a single command is more efficient.

---

## Commands Used

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null

cat /var/lib/dpkg/info/bandit7.password
```

---

## Why These Commands?

| Command | Purpose |
|---------|---------|
| `find` | Locate files matching multiple criteria |
| `cat` | Read the contents of the password file |

---

## Skills Learned

- Advanced Linux Enumeration
- Searching by Owner and Group
- Searching by File Size
- Error Redirection
- Reading Files

---

## Tools Used

- SSH
- Linux Terminal
- find
- cat

---

## Notes

### What is `/dev/null`?

`/dev/null` is a special device that discards anything written to it.

It is commonly used to suppress unwanted output.

Example:

```bash
command 2>/dev/null
```

This hides only error messages.

To hide both normal output and errors:

```bash
command > /dev/null 2>&1
```

Understanding output redirection is an essential Linux skill and is frequently used during penetration testing and system administration.

---

## Password

```text
Password intentionally omitted.
```