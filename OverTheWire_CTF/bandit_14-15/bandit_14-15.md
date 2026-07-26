# 🌐 Bandit Level 14 → Level 15

**Platform:** OverTheWire  

**Category:** Networking  

**Difficulty:** 🟡 Medium

## Challenge Description

Retrieve the password for the next level by submitting the current level's password to **port 30000** on **localhost**.

## Solution

First, retrieve the current password:

```bash
cat /etc/bandit_pass/bandit14
```

```text
aaWecNkG4FhxJQxz07uiwzVP6bJiYS65
```

An attempt to connect using SSH on port **30000** fails because the service running on that port is **not an SSH server**:

```bash
ssh bandit14@localhost -p 30000
```

```text
Connection closed by 127.0.0.1 port 30000
```

Check the available options for **Netcat (nc)**:

```bash
nc -h
```

An incorrect attempt using the `-x` option displays the command usage:

```bash
nc -x localhost:30000
```

Finally, establish a TCP connection to the service using Netcat:

```bash
nc localhost 30000
```

After the connection is established, submit the current password:

```text
aaWecNkG4FhxJQxz07uiwzVP6bJiYS65
```

Server response:

```text
Correct!
Password intentionally omitted.
```

The returned value is the password for **Bandit Level 15**.

## Commands Used

| Command | Purpose |
|---------|---------|
| `cat` | Read the current level password |
| `ssh` | Test whether port 30000 provides an SSH service |
| `nc -h` | View Netcat usage information |
| `nc localhost 30000` | Connect to the TCP service on port 30000 |

## Skills Learned

- Connecting to TCP services with Netcat (`nc`)
- Difference between SSH services and generic TCP services
- Using localhost and custom ports
- Sending input to a listening network service

## Tools Used

- Linux Terminal
- Netcat (`nc`)
- SSH

## Password

```text
Password intentionally omitted.
```