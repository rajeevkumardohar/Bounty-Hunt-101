# 🛡️ Bounty Hunt 101 — Bug Hunt (Recon to Report)

## Author
- **Name:** Rajeev Kumar
- **Lab:** Damn Vulnerable Web Application (DVWA)
- **Environment:** Apache + PHP + MariaDB (Termux, Localhost)

---

## 📌 Project Overview
This project demonstrates a complete beginner-level bug bounty workflow in a controlled lab environment.
The goal was to identify, exploit, and document common web vulnerabilities safely.

---

## 🔍 Reconnaissance
Basic service enumeration was performed on the local DVWA instance using Nmap.

**Target:** localhost  
**Tool:** Nmap

Open services identified:
- **80/tcp** – HTTP (Apache Web Server)
- **3306/tcp** – MySQL (MariaDB)

See full output in `recon/nmap-scan.txt`.

---

## 🐞 Vulnerability Findings

---

### 1️⃣ Reflected Cross-Site Scripting (XSS)

- **Module:** XSS (Reflected)
- **Security Level:** Low
- **Payload:**

**Description:**  
User input is reflected in the response without proper sanitization, allowing execution of arbitrary JavaScript.

**Impact:**  
An attacker can execute malicious scripts in the victim’s browser, potentially leading to session hijacking or phishing.

**Evidence:**  
Screenshots available in the `xss/` directory.

---

### 2️⃣ SQL Injection (SQLi)

- **Module:** SQL Injection
- **Security Level:** Low
- **Payload:**

**Description:**  
Improper input validation allows manipulation of SQL queries, resulting in disclosure of multiple database records.

**Impact:**  
An attacker can access sensitive data, bypass access controls, and compromise database integrity.

**Evidence:**  
Screenshots available in the `sqli/` directory.

---

### 3️⃣ Insecure Direct Object Reference (IDOR) / CSRF

- **Module:** CSRF
- **Security Level:** Low

**Description:**  
Sensitive account actions such as password change are performed using HTTP GET parameters without CSRF protection or additional authorization checks.

**Impact:**  
An attacker can force authenticated users to unknowingly change their account credentials, leading to account compromise.

**Evidence:**  
URL-based request and vulnerable source code available in the `idor/` directory.

---

## ✅ Conclusion
This project successfully demonstrates the identification and exploitation of common web vulnerabilities using a structured bug bounty approach.
It highlights the importance of secure coding practices and proper access control mechanisms.

---

## ⚠️ Disclaimer
All testing was performed in a deliberately vulnerable lab environment for educational purposes only.

## 🛠 Tools Used
- Nmap
- Browser DevTools
- Manual Payload Testing

## 📚 What I Learned
- How reconnaissance helps identify attack surface
- How improper input validation leads to XSS & SQLi
- Importance of CSRF protection
