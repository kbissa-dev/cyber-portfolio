# TryHackMe — OWASP Top 10 (2025): Application Design Flaws

## Goal
Work through four small web apps and spot common mistakes: debug leaks, unsafe dependencies, weak crypto,
and “mobile-only” API assumptions.

## Tools I used
- Browser (to read pages + view source)
- `curl` (to talk to the API directly)
- `gobuster` (to discover hidden API routes)
- `python3` (to reproduce decryption)

## What I learned
### 1) Debug / trace leaks are dangerous
When I sent unexpected input to an endpoint, the app printed internal debug details. 
That kind of output can reveal how the backend works and sometimes includes secrets.

**Fix:** turn off debug output, handle errors safely, don’t expose stack traces to users.

### 2) “Debug” behaviour in services is risky (supply chain / outdated code story)
The processing API behaved normally for normal data, but special input triggered extra internal information. 
That’s the kind of thing that should never be reachable from the public internet.

**Fix:** remove debug paths, validate inputs, add auth checks, and review dependency code.

### 3) Crypto fails if secrets are shipped to the browser
The encryption key was visible in a JavaScript file and the mode was ECB. 
Once I had the key + mode, I could decrypt the document offline.

**Fix:** never put secret keys in client-side code, avoid ECB, use modern modes like AES-GCM, and manage keys properly.

### 4) “Mobile-only” is not a security control
The app assumed only a mobile client would call the backend. 
But the backend API could be accessed directly without login, which is the real problem.

**Fix:** enforce authentication + authorization on the server for every endpoint.

## Evidence
Screenshots are stored in `writeups/tryhackme/images/` (no flags).
