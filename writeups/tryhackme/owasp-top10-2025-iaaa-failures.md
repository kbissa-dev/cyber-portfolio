# TryHackMe — OWASP Top 10 (2025): IAAA Failures

## Objective
Understand how weaknesses in Identity, Authentication, Authorisation, and Accountability (IAAA) can lead to real security issues in web applications.

This room helped me see how small design mistakes — not complex exploits — can break security controls.

---

## Tools Used
- Browser developer tools
- curl (to interact directly with endpoints)
- Log review
- Manual URL manipulation

---

## Key Security Issues Observed

### 1. Broken Access Control (A01)

By modifying an ID value in the URL, I was able to view another user's account information. 
There were no proper server-side checks validating whether the authenticated user was authorised to access that data.

**Why this matters**
If access control is enforced only on the client side, attackers can bypass it easily.

**Fix**
- Enforce authorization checks on every request (server-side)
- Avoid predictable object identifiers
- Validate resource ownership before returning data

---

### 2. Authentication Failures (A07)

The login system allowed repeated password attempts without lockout or rate limiting. 
Eventually, authentication succeeded after multiple attempts.

**Why this matters**
Without rate limiting or monitoring, brute-force attacks become practical.

**Fix**
- Implement rate limiting
- Account lockout after failed attempts
- Enforce strong password policies
- Add multi-factor authentication

---

### 3. Identity Handling Logic Issue

The system did not properly normalise usernames. 
Different variations of a privileged username were treated inconsistently between registration and login processes.

**Why this matters**
Improper identity handling can create account confusion and unintended access paths.

**Fix**
- Normalise usernames before storage and comparison
- Enforce strict uniqueness rules
- Perform identity validation consistently server-side

---

### 4. Logging & Accountability Failures (A09)

Application logs showed repeated login attempts from a single external IP address.

However:
- No alerting was triggered
- No blocking occurred
- The attack could only be identified through manual review

**Why this matters**
Without proper monitoring and alerting, attacks may go unnoticed.

**Fix**
- Centralised logging
- Alert on repeated failed authentication attempts
- Monitor authentication anomalies

---

## What I Learned

Before this lab, I mostly focused on “finding bugs.” 
This room helped me understand how **design assumptions** create security failures.

Key learning points:
- Access control must always be enforced server-side
- Authentication logic must handle identity consistently
- Predictable identifiers often lead to horizontal privilege escalation (IDOR)
- Logging is not optional — it is critical for detection and investigation

I also learned to distinguish between:
- Horizontal privilege escalation (accessing another user's data)
- Vertical privilege escalation (gaining higher privileges)

---

## Skills Demonstrated
- Access control testing
- Authentication flow analysis
- Log investigation
- Mapping findings to OWASP Top 10 categories
- Identifying horizontal privilege escalation (IDOR)

---

## OWASP Mapping
- A01: Broken Access Control 
- A07: Authentication Failures 
- A09: Security Logging & Monitoring Failures 

---

## Note
This write-up focuses on vulnerability understanding and remediation concepts rather than step-by-step exploitation details.
