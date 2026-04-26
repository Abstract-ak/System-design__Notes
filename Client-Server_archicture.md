# 🌐 What Happens When You Open a Website (System Design Basics)

## 📌 Example

When you enter:

```
https://google.com
```

---

## 1️⃣ Browser Checks Cache

Before doing anything, the browser checks:

- Browser cache
- OS DNS cache

👉 If found, it skips DNS lookup → faster response.

---

## 2️⃣ DNS Resolution (Domain → IP Address)

### 📷 Visual Reference

![DNS Resolution](https://source.unsplash.com/800x450/?dns,network)

### 🔍 Process

DNS converts domain name → IP address.

Steps:

1. Browser → DNS Resolver (ISP)
2. Resolver → Root Server (Where is `.com`?)
3. Root → TLD Server (`.com`)
4. TLD → Authoritative Server (`google.com`)
5. Returns IP Address

```
google.com → 142.250.xxx.xxx
```

👉 This is called **recursive DNS lookup**

---

## 3️⃣ TCP Connection + TLS Handshake

### 📷 Visual Reference

![TCP TLS Handshake](https://source.unsplash.com/800x450/?https,security)

### 🔗 TCP Handshake (3-way)

- SYN
- SYN-ACK
- ACK

### 🔒 TLS Handshake (HTTPS only)

- Verify SSL Certificate
- Exchange encryption keys
- Secure connection established

---

## 4️⃣ HTTP Request Sent

Browser sends request:

```
GET / HTTP/1.1
Host: google.com
```

---

## 5️⃣ Server-Side Processing

### 📷 Visual Reference

![Server Architecture](https://source.unsplash.com/800x450/?server,architecture)

### 🏗️ Flow

- Request hits **Load Balancer**
- Routed to **Web Server**
- Calls:
  - Application Server
  - Database
  - Cache (Redis)

---

## 6️⃣ Server Response

Server returns:

- HTML
- CSS
- JavaScript

👉 Browser renders the UI

---

## 🎯 Final Flow Summary

```
User → Browser → DNS → IP
→ TCP + TLS → HTTP Request
→ Server → Response → Render
```

---

## ⚠️ Key Clarifications

- DNS is **hierarchical lookup**, not string matching
- `.com` is a **TLD (Top-Level Domain)**, not a condition check
- HTTPS adds **security via encryption**

---

## 🧠 Interview-Ready Answer

> When a user enters a URL, the browser first checks local cache. If not found, it performs DNS resolution to get the IP address. Then it establishes a TCP connection and performs a TLS handshake for secure communication. After that, it sends an HTTP request to the server. The request is processed through load balancers and backend services, and the server responds with HTML, CSS, and JavaScript, which the browser renders.

---

## 🚀 Next Topic

👉 Difference between **HTTP vs HTTPS**
