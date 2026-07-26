# 🔒 Bandit Level 15 → Level 16

**Platform:** OverTheWire Bandit  

**Category:** Networking / SSL  

**Difficulty:** 🟡 Medium

## 🎯 Goal
Retrieve the password for **Bandit Level 16** by sending the current level's password to **localhost:30001** over an **SSL/TLS** connection.

---

## 🛠️ Tools
- `openssl`
- `s_client`

---

## ⚡ Solution

Unlike the previous level, the service requires an encrypted SSL/TLS connection instead of a normal TCP connection.

Connect using:

```bash
openssl s_client -connect localhost:30001
```

After the SSL handshake completes, paste the **Bandit15** password and press **Enter**.

The server validates the password and returns the password for **Bandit16**.

---

## 📋 Commands Used

| Command | Purpose |
|---------|---------|
| `openssl s_client -connect localhost:30001` | Connect to the SSL/TLS service |
| *(paste current password)* | Authenticate with the service |

---

## 📚 Skills Learned
- SSL/TLS connections
- Using `openssl s_client`
- Interacting with encrypted network services

---

## 🚩 Flag / Password

```text
<Bandit16 Password>
```