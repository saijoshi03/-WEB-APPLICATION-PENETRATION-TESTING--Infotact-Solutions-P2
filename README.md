# Web Application Penetration Testing (OWASP Top 10 Focus)

##  Project Overview
This project focuses on performing **web application penetration testing** using the **Damn Vulnerable Web Application (DVWA)** hosted on the **TryHackMe** platform.  
It aims to explore and exploit common OWASP Top 10 vulnerabilities, including **SQL Injection**, **XSS**, **Command Injection**, **Brute Force**, and **CSRF**.

 **Full Report:**  
View PDF Report -::

---

##  Tools & Platforms Used
- **TryHackMe** – Online cybersecurity lab environment  
- **DVWA** – Target vulnerable web application  
- **Kali Linux** – Attacker machine  
- **Burp Suite (Community Edition)** – Proxy interception and exploitation  
- **Web Browser (Firefox/Chrome)** – To access and test the DVWA application  

---

##  Environment Setup
1. Logged into TryHackMe and joined the **DVWA Room**  
2. Launched the AttackBox / connected VPN  
3. Accessed target machine using `http://10.201.120.56/login.php`  
4. Verified connectivity between attacker and target  

---

##  Vulnerability Testing Performed

###  1. Brute Force — *OWASP A07: Identification & Authentication Failures*
- Attempted login brute-force using **Burp Intruder**
- Successfully identified valid admin credentials

###  2. Command Injection — *OWASP A03: Injection*
- Executed `127.0.0.1; cat /etc/passwd`  
- Extracted sensitive data demonstrating command injection vulnerability

###  3. SQL Injection — *OWASP A03: Injection*
- Injected `' OR '1'='1'#` payload  
- Bypassed login filter and retrieved database content

###  4. XSS (Cross-Site Scripting) — *OWASP A03: Injection*
- Injected `<script>alert(document.cookie)</script>` payload  
- Successfully executed client-side script (Stored XSS)

###  5. CSRF (Cross-Site Request Forgery) — *OWASP A05: Security Misconfiguration*
- Crafted a malicious HTML file that auto-changes user password  
- Demonstrated successful CSRF attack when victim clicks the link

---

##  Recommendations
1. Implement **input validation** and **parameterized queries** to prevent injection attacks.  
2. Use **CSRF tokens** in all critical requests.  
3. Apply **rate limiting** and **multi-factor authentication** for login pages.  
4. Sanitize and encode all **user-supplied input** to prevent XSS.  
5. Disable **command execution functions** (e.g., `system()`, `exec()`) unless absolutely necessary.  

---

##  Team Members
- **Saikumar Joshi[team leader]**  
- **Alex Jose**  
- **Manas Veetil**  
- **Afrin A N**

---

##  Learning Outcome
- Gained hands-on experience exploiting OWASP Top 10 vulnerabilities.  
- Learned to use **Burp Suite**, **TryHackMe**, and **DVWA** effectively for web app security testing.  
- Developed understanding of real-world attack vectors and mitigations.
