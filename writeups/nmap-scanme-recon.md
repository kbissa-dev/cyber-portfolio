====================================
PENETRATION TEST REPORT
Target: scanme.nmap.org (45.33.32.156)
Date: 27 February 2026
Tester: Khushboo
Tool: Nmap 7.95
====================================

OBJECTIVE:
Perform network reconnaissance on an authorized 
target to identify open ports, running services,
and potential vulnerabilities.

FINDINGS:
1. Port 22 - OpenSSH 6.6.1p1 [HIGH RISK]
   - Ooutdated version with known CVEs
   - EDB-45001: Remote Code Execution possible
   - CVE-2014-2532: Environment bypass

2. Port 80 - Apache httpd 2.4.7 [HIGH RISK]
   - Ooutdated version with known CVEs
   - CVE-2017-9798: Memory disclosure
   - Server version exposed in HTTP header

3. Port 25 - SMTP [FILTERED]
   - Blocked by firewall - good practice

4. SSH Key Weakness [MEDIUM RISK]
   - 1024-bit DSA key in use
   - Below modern recommended strength

OS DETECTED: Linux 4.19-5.15 (95% confidence)
NETWORK DISTANCE: 20 hops (Australia to USA)

RECOMMENDATIONS:
- Upgrade OpenSSH to latest version
- Upgrade Apache to latest version  
- Remove server version from HTTP headers
- Replace 1024-bit DSA key with ED25519

CONCLUSION:
Target has multiple outdated services with 
documented exploits. Priority remediation 
recommended for ports 22 and 80.
====================================
