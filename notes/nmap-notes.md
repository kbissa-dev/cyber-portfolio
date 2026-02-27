# Nmap Study Notes

## What is Nmap
Tool for scanning networks — finds what hosts are alive,
what ports are open, what software is running.
Used in recon phase of every pentest.

## Port States
- open — something is listening, investigate
- closed — nothing running there
- filtered — firewall blocking it

## Commands I Use
1. nmap scanme.nmap.org              — basic scan, found 5 ports
2. nmap -sV scanme.nmap.org          — found OpenSSH 6.6.1 + Apache 2.4.7
3. sudo nmap -A scanme.nmap.org      — full scan, OS detection, traceroute
4. nmap -A target -oN report.txt     — save output to file

### Every Scan Type - When and Why
1. Basic TCP Connect scan (Default)
nmap <target>

2. Find software versions - Every Version has CVE history.
 Old version = known vulnerabilities = potential exploit
nmap -sV <target>

3. Full scan with OS detection
sudo nmap -A <target>

4. SYN Stealth scan - Most Important for Pentesters
sudo nmap -sS <target>

5. Aggressive Scan (-A) - Full Report Scan
 sudo nmap -A <target>
Combines everything: -sV + -O + --traceroute + default scripts.

6. UDP Scan
sudo nmap -sU <target>
Much slower than TCP (can take hours on a full scan). 
Important because many critical service run on UDP. 

#### Save output
nmap -A <target> -oN scan.txt

## What I Learned From Scanning scanme.nmap.org
- Port 22 open — SSH running
- Port 80 open — Apache web server
- Found outdated versions — searched CVEs on exploit-db
- Traceroute showed 20 hops Australia to USA

## CVE Research Process
1. Note open ports and versions from scan
2. Search nvd.nist.gov or cvedetails.com
3. Check exploit-db.com for working exploits
4. Use searchsploit in Kali for offline search
5. Document findings with risk rating

## Resources
- nvd.nist.gov
- exploit-db.com  
- cvedetails.com


