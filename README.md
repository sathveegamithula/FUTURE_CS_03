# FUTURE_CS_03
API Security Risk Analysis
# 🔒 API Security Risk Analysis

## 📌 Project Overview
This project presents a read-only API Security Risk Analysis conducted on the public test API:  
👉 https://jsonplaceholder.typicode.com  

The assessment was performed as part of the Future Interns Cybersecurity Programme – Task 3 (2026) to identify common API vulnerabilities and explain their real-world business impact.

---

## 👩‍💻 Author
Sathveega Mithula

---

## 🎯 Objective
- Analyze API endpoints for security risks  
- Identify vulnerabilities based on OWASP API Security Top 10 (2023)  
- Provide clear remediation strategies  
- Demonstrate practical API security testing skills  

---

## 🔍 Scope of Testing

### Tested Endpoints
- /users – Fetch all users  
- /users/{id} – Fetch user by ID  
- /posts – Fetch all posts  
- /comments – Fetch all comments  

### Tools Used
- Postman

### Methodology
- API documentation review  
- Sending GET requests  
- Response and header analysis  
- Authentication & authorization checks  
- Data exposure evaluation  
- Risk classification (High / Medium / Low)  

---

## 🚨 Key Findings

A total of 6 security risks were identified:

| Severity | Count |
|----------|------|
| 🔴 High   | 3    |
| 🟠 Medium | 2    |
| 🟡 Low    | 1    |

---

## ⚠️ Identified Vulnerabilities

### 🔴 High Severity
- Unauthenticated Access
  - All endpoints accessible without login
- Excessive Data Exposure
  - Sensitive user data (PII) returned unnecessarily
- IDOR (Insecure Direct Object Reference)
  - Users accessible by simply changing ID in URL

### 🟠 Medium Severity
- Missing Rate Limiting
  - Unlimited requests → risk of abuse & DoS
- Email Exposure
  - Emails visible in /comments endpoint

### 🟡 Low Severity
- Missing Security Headers
  - No HSTS, CSP, or clickjacking protection

---

## 💥 Business Impact
If these vulnerabilities exist in a real production system:
- Data breaches and privacy violations  
- GDPR / PDPA compliance issues  
- Increased risk of phishing and spam attacks  
- Infrastructure overload and service downtime  
- Reputation damage  

---

## 🛠️ Recommendations

### 1. Implement Authentication
- Use JWT or OAuth 2.0
- Return 401 Unauthorized for invalid requests  

### 2. Enforce Authorization
- Validate user access before returning data  
- Prevent ID-based data exposure  

### 3. Apply Data Minimization
- Return only necessary fields  
- Remove sensitive data (emails, addresses, etc.)  

### 4. Enable Rate Limiting
- Limit requests (e.g., 100 req/min)  
- Return 429 Too Many Requests  

### 5. Add Security Headers
- Strict-Transport-Security  
- Content-Security-Policy  
- X-Frame-Options  
- X-Content-Type-Options  

---

## 📊 Conclusion
This project highlights common API security flaws found in modern applications.  
The most critical issues—authentication, authorization, and data exposure—must be addressed immediately in any production environment.

This analysis demonstrates:
- Practical API testing  
- Risk assessment skills  
- Security best practices using OWASP standards  

---

## 📚 References
- OWASP API Security Top 10 (2023)  
- JSONPlaceholder API  
- Shieldfy API Security Checklist  
- Postman API Tool  

---

## ⭐ Notes
- This assessment was read-only and ethical  
- No exploitation or harmful testing was performed  
- The API is intentionally insecure for learning purpose
