# 🥪 SUDO MAKE ME A SANDWICH

**Platform:** PicoCTF

**Category:** General Skills

**Difficulty:** 🟢 Easy

## Challenge Description
The challenge provides SSH access to a remote machine. The objective is to read a protected `flag.txt` file.

## Solution

After connecting via SSH, verify that the flag exists:
```bash
ls
```

Attempting to read the file directly results in a permission error:
```bash
cat flag.txt
```
```text
cat: flag.txt: Permission denied
```

Check the current user:
```bash
whoami
```
```text
ctf-player
```

Inspect the file permissions:
```bash
ls -l
```
```text
-r--r----- 1 root root 31 Mar 9 21:31 flag.txt
```

The file is owned by **root**, so the current user cannot read it directly.

Trying to start a root shell is denied:
```bash
sudo -i
```
```text
Sorry, user ctf-player is not allowed to execute '/bin/bash' as root.
```

Instead of requesting a root shell, use `sudo` to execute the `cat` command directly, since the sudoers policy allows that specific command:
```bash
sudo cat flag.txt
```

The command prints the contents of the flag file.

## Skills Learned
- Linux File Permissions
- File Ownership
- sudo Privileges
- Basic Linux Enumeration

## Tools
- SSH
- Linux Terminal

## Flag
```text
picoCTF{hidden}
```
