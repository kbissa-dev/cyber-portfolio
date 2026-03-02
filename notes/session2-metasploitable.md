# Session 2 — Metasploitable2 Lab Setup & Service Enumeration
# (VirtualBox)

## What I did

- Deployed Metasploitable2 in VirtualBox and confirmed boot/login.

- Configured an isolated lab network and validated host-to-VM connectivity.

- Ran service discovery and deeper enumeration scans with Nmap.

- Documented exposed services, versions, and high-risk configurations.

- Researched known security advisories for defensive understanding (verification + mitigation planning).

### Key findings (high level)

- Target (lab VM): 172.30.30.10

- OS fingerprinting: Unix/Linux; Samba service identified (Samba 3.x family detected)

- Notable exposed services: FTP (vsftpd), SMB/Samba, Telnet, SMTP, SSH

### Risk themes:

- Legacy/insecure services (e.g., Telnet)

- Weak SMB configuration signals (e.g., SMB signing not enforced)

- Multiple services increase attack surface and misconfiguration risk

#### What went wrong (and how I handled it)

- Initial connectivity issues due to VirtualBox adapter mode / interface routing.

- Fixed by aligning both VMs on the same Internal Network and validating the correct
 interface selection (ip route get, ping, targeted Nmap).

##### What I learned - Key Insights

> “Tool ran” ≠ “objective achieved” — always validate with 
> independent checks (route, ping, port state).

- Network design (NAT vs Internal) changes what is reachable and from where.

- Enumeration is about evidence-based risk: service + version + configuration → likely weaknesses → mitigations
