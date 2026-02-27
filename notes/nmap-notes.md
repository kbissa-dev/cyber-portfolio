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

### Basic scan
nmap <target>

### Find software versions
nmap -sV <target>

### Full scan with OS detection
sudo nmap -A <target>

### Stealth scan
sudo nmap -sS <target>

### Save output
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


