# 🛡️ SOC Analyst Fundamentals Notes

## 📌 1. Networking Basics

### Common Ports & Protocols

| Port | Protocol | Use                       |
| ---- | -------- | ------------------------- |
| 21   | FTP      | File transfer             |
| 22   | SSH      | Secure remote login       |
| 25   | SMTP     | Sending emails            |
| 53   | DNS      | Domain resolution         |
| 80   | HTTP     | Web traffic (unencrypted) |
| 110  | POP3     | Receiving emails          |
| 443  | HTTPS    | Secure web traffic        |
| 445  | SMB      | Windows file sharing      |
| 3389 | RDP      | Remote desktop            |

---

## 📌 2. TCP vs UDP

* **TCP**

  * Connection-oriented
  * Reliable
  * Uses 3-way handshake:

    ```
    SYN → SYN-ACK → ACK
    ```

* **UDP**

  * Connectionless
  * Faster but unreliable

---

## 📌 3. Types of Attacks

### 🔹 Brute Force

* Same user → many password attempts
* Example:

  ```
  Failed password for admin
  ```

---

### 🔹 Password Spraying

* One password → many users
* Avoids account lockout

---

### 🔹 Port Scanning

* Scanning multiple ports quickly
* Example:

  ```
  Ports: 21,22,80,443
  ```

---

### 🔹 Web Enumeration

* Trying multiple URLs:

  ```
  /admin
  /login
  /config
  ```

---

### 🔹 Data Exfiltration

* Large data transfer to external IP

---

## 📌 4. SOC Concepts

### SIEM

Security Information and Event Management

* Collects logs
* Detects patterns
* Generates alerts

---

### Logs

Example:

```
Failed password for root from 185.220.101.4 port 45321 ssh2
```

Breakdown:

| Field           | Meaning     |
| --------------- | ----------- |
| Failed password | Action      |
| root            | Target user |
| IP              | Attacker    |
| ssh2            | Protocol    |

---

## 📌 5. Alert Types

| Type           | Meaning             |
| -------------- | ------------------- |
| True Positive  | Real attack         |
| False Positive | Alert but no attack |
| False Negative | Attack but no alert |

---

## 📌 6. MITRE ATT&CK Stages

```
Reconnaissance
Initial Access
Persistence
Privilege Escalation
Lateral Movement
Defense Evasion
Command & Control
Exfiltration
```

---

## 📌 7. Attack Chain Example

```
Port Scan
↓
Brute Force
↓
Successful Login
↓
New Admin Account
↓
Outbound Connection
```

---

## 📌 8. Lateral Movement

* Moving between systems inside network
* Example:

  ```
  Workstation → Server → Database
  ```

Common methods:

* RDP
* SSH
* SMB

---

## 📌 9. Defense Evasion Techniques

* Disable antivirus
* Clear logs
* Use PowerShell (living off the land)
* Encode commands
* Rename malware

---

## 📌 10. Threat Intelligence

### IOC (Indicators of Compromise)

* IP address
* Domain
* File hash

Example:

```
185.220.101.4
```

Used to check:

* reputation
* past attacks
* malware links

---

## 📌 11. Command & Control (C2)

* Infected system connects to attacker server
* Used for:

  * commands
  * data transfer
  * malware download

---

## 📌 12. Common Log Patterns

### SSH Brute Force

```
Failed password
Failed password
Failed password
```

---

### Successful Compromise

```
Accepted password
```

---

### Persistence

```
New user account created
Scheduled task created
```

---

### Suspicious Behavior

```
PowerShell executed
Encoded command
Unknown external connection
```

---

## 📌 13. SOC Investigation Steps

1. Identify alert
2. Analyze logs
3. Check IP reputation
4. Verify if attack succeeded
5. Investigate impact
6. Escalate if needed

---

## 📌 14. Key Analyst Questions

```
What happened?
Is it malicious?
What should we do next?
```

---

## 📌 15. Important Concepts

* **Initial Access** → attacker enters system
* **Persistence** → attacker maintains access
* **Privilege Escalation** → gains higher rights
* **Lateral Movement** → spreads inside network
* **Defense Evasion** → hides activity
* **C2** → communicates with attacker
* **Exfiltration** → steals data

---

## 🚀 Final Note

To become SOC-ready:

* Practice log analysis daily
* Understand attack patterns
* Think like an investigator
* Focus on hands-on learning

---

🔥 This is your core SOC foundation.
