# 🌐 Networking + Web Security – Quick Revision Notes

---

# 🔑 Common Networking Ports

| Port | Protocol | Purpose |
|------|----------|--------|
| 21 | FTP | File transfer (insecure) |
| 22 | SSH | Secure remote login |
| 23 | Telnet | Remote login (insecure) |
| 25 | SMTP | Send email |
| 53 | DNS | Domain → IP |
| 80 | HTTP | Web browsing |
| 110 | POP3 | Download emails |
| 143 | IMAP | Access emails |
| 443 | HTTPS | Secure web |
| 445 | SMB | File sharing |
| 3389 | RDP | Remote desktop |
| 3306 | MySQL | Database |

### ⚠️ Port Categories
- **0–1023** → Well-known  
- **1024–49151** → Registered  
- **49152–65535** → Dynamic  

---

# 🚨 Malware / Suspicious Ports

| Port | Use |
|------|-----|
| 12345 | NetBus (backdoor) |
| 27374 | SubSeven |
| 31337 | Back Orifice |
| 4444 | Metasploit shell |
| 5555 | Android debug abuse |
| 6667 | IRC botnet |
| 8080 | Alternative HTTP |
| 9001 | Tor traffic |

---

# 🌐 TCP vs UDP

## TCP
- Connection-oriented  
- Reliable  
- Ordered delivery  
- Uses **3-way handshake (SYN → SYN-ACK → ACK)**  

## UDP
- Connectionless  
- Faster  
- No guarantee of delivery  
- No ordering  

### ⚡ Difference

| Feature | TCP | UDP |
|--------|----|----|
| Reliability | Yes | No |
| Speed | Slower | Faster |
| Connection | Required | Not required |

🧠 **Memory:**  
- TCP → Trust & Check  
- UDP → Ultra-fast  

---

# 🌐 HTTP Basics

## What is HTTP?
Protocol for communication between **client ↔ server**

```
Client → Request → Server
Server → Response → Client
```

---

## 📩 HTTP Request Structure
- Method (GET / POST)  
- URL  
- Headers  
- Body (optional)  

---

# 📥 GET vs POST

## GET
- Retrieve data  
- Parameters in URL  
- Cacheable  

Example:
```
GET /products?id=10
```

## POST
- Send data  
- Data in body  
- Used for login/forms  

Example:
```
POST /login
username=indu&password=123
```

---

# 🌐 HTTP Status Codes

## Categories

| Range | Meaning |
|------|--------|
| 1xx | Info |
| 2xx | Success |
| 3xx | Redirect |
| 4xx | Client error |
| 5xx | Server error |

## Important Codes

| Code | Meaning |
|------|--------|
| 200 | OK |
| 201 | Created |
| 301 | Permanent redirect |
| 302 | Temporary redirect |
| 400 | Bad request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not found |
| 500 | Server error |
| 503 | Service unavailable |
| 505 | HTTP version not supported |

🧠 Memory:
- 200 → Success  
- 400 → Client issue  
- 500 → Server issue  

---

# 📩 HTTP Headers

## Request Headers

| Header | Purpose |
|--------|--------|
| Host | Domain name |
| User-Agent | Client info |
| Accept | Data type |
| Authorization | Auth credentials |
| Cookie | Session data |

## Response Headers

| Header | Purpose |
|--------|--------|
| Content-Type | Data type |
| Set-Cookie | Send session |
| Server | Server info |

---

# 🔐 Login Flow (Step-by-Step)

1. GET `/login` → Load page  
2. User enters credentials  
3. POST `/login` → Send data  
4. Server verifies  
5. Server sends cookie  
6. Browser stores cookie  
7. Future requests include cookie  

Example:
```
Cookie: sessionid=abc123
```

---

# 🚨 Web Attacks (Login)

- **Brute Force** → Multiple attempts  
- **SQL Injection** → `' OR 1=1`  
- **Session Hijacking** → Steal cookies  

---

# 🌐 DNS (Domain Name System)

Converts:
```
google.com → IP address
```

## Resolution Flow

1. Browser cache  
2. OS cache  
3. DNS resolver  
4. Root server  
5. TLD server (.com)  
6. Authoritative server  
7. IP returned  

---

## 🔐 DNS Attacks

- DNS Spoofing  
- DNS Amplification  
- DNS Tunneling  

---

# 🌐 Web Log Analysis

## Log Example
```
127.0.0.1 - - [10/Mar/2026] "GET /index.html HTTP/1.1" 200 1024
```

## Fields

| Field | Meaning |
|------|--------|
| IP | Client IP |
| Timestamp | Time |
| Method | GET/POST |
| URL | Resource |
| Status | Response |
| Size | Data size |

---

## 🚨 Suspicious Patterns

### Brute Force
```
POST /login (repeated)
```

### SQL Injection
```
admin'--
```

### XSS
```
<script>alert(1)</script>
```

### Directory Traversal
```
../../etc/passwd
```

### Scanning
```
/admin
/phpmyadmin
```

---

## 🔍 Analysis Tips

- Repeated IP activity  
- Strange User-Agent  
- High request rate  
- Suspicious payloads  

---

## 🧠 Summary

- Ports identify services  
- TCP vs UDP defines communication  
- HTTP handles web requests  
- DNS resolves domains  
- Logs help detect attacks  

👉 Web logs = **key evidence in cyber forensics**
