# 🌍 Bandit Level 6 → 7

**Platform:** OverTheWire
**Category:** Linux File Enumeration
**Difficulty:** 🟡 Medium

---

## Challenge Description

The password for the next level is stored somewhere on the server, owned by user `bandit7`, owned by group `bandit6`, and exactly **33 bytes** in size.

---

## Approach

Since the target file isn't in the current directory, the search must start from the filesystem root (`/`). Searching manually across the entire filesystem is impractical, so `find` is used with ownership and size filters combined. Many system directories aren't readable by a regular user, so error output is suppressed to keep results clean.

---

## Solution

Search the entire filesystem for a match:

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

```text
/var/lib/dpkg/info/bandit7.password
```

Read the discovered file:

```bash
cat /var/lib/dpkg/info/bandit7.password
```

The output contains the password for the next level.

---

## Skills Learned

- System-wide search with `find /`
- Filtering by owner and group
- Suppressing errors with `2>/dev/null`

---

## Tools

- SSH
- Linux Terminal
- `find`
- `cat`

---

## Password

```text
Password intentionally omitted.
```
