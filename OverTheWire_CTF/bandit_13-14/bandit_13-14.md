# 🔑 Bandit Level 13 → Level 14

**Platform:** OverTheWire  

**Category:** Linux / SSH  

**Difficulty:** 🟡 Medium

## Challenge Description

Authenticate as **bandit14** using the provided SSH private key, then retrieve the password stored in `/etc/bandit_pass/bandit14`.

## Solution

List the available files:

```bash
ls
```

```text
HINT
sshkey.private
```

Read the hint and verify the key type:

```bash
cat HINT
file sshkey.private
```

```text
sshkey.private: OpenSSH private key
```

Attempting to authenticate from the Bandit machine:

```bash
ssh -i sshkey.private bandit14@localhost -p 2220
```

Result:

```text
Connecting from localhost is blocked.
Please log out and log in again.
```

The error indicates that the SSH key must be used **from the local machine**, not from inside the Bandit server.

Copy the private key to the local system using `scp`:

```bash
scp -P 2220 bandit13@bandit.labs.overthewire.org:~/sshkey.private .
```

When trying to authenticate locally:

```bash
ssh -i sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org
```

SSH returned:

```text
WARNING: UNPROTECTED PRIVATE KEY FILE!
Permissions ... are too open.
This private key will be ignored.
```

On Windows, restrict the private key permissions so that only the current user can access it (or use `icacls`).

After fixing the permissions, authenticate again:

```bash
ssh -i sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org
```

Finally, retrieve the next password:

```bash
cat /etc/bandit_pass/bandit14
```

## Commands Used

| Command | Purpose |
|---------|---------|
| `ls` | List available files |
| `cat` | Read the hint |
| `file` | Verify the key type |
| `scp` | Copy the private key to the local machine |
| `ssh -i` | Authenticate using the private key |
| `icacls` | Fix Windows file permissions |
| `cat /etc/bandit_pass/bandit14` | Read the next password |

## Skills Learned

- SSH Key Authentication
- Using `scp` for secure file transfer
- Using `ssh -i`
- Windows file permissions (`icacls`)
- Troubleshooting SSH authentication errors

## Tools Used

- Linux Terminal
- Windows CMD
- SSH
- SCP

## Password

```text
Password intentionally omitted.
```