# TryHackMe — Juicy Details

## Overview
This room was a beginner-friendly SOC log analysis exercise. The goal was to work through log files and understand what an attacker did inside a Juice Shop environment.

I used this room to practise reading logs, spotting suspicious patterns, and connecting events across multiple services instead of guessing answers.

## Logs I looked at
- `access.log` — web requests, endpoints, response codes, and user-agents
- `auth.log` — login attempts and successful authentication events
- `vsftpd.log` — FTP logins and file download activity

## What I found
From the logs, I identified several attacker actions:

- Reconnaissance activity using **nmap**
- Brute-force attempts using **hydra**
- SQL injection attempts using **sqlmap**
- Manual retrieval of data with **curl**
- Directory and file discovery using **feroxbuster**

I also found:
- a brute-force target at `/rest/user/login`
- SQL injection attempts against `/rest/products/search`
- the SQL injection parameter was `q`
- file access through the `/ftp` endpoint

## How I understood the attack
The biggest lesson from this room was that I do not need to read every single line in a huge log file.

Instead, I learned to:
- start with the question
- choose the right log file
- search for useful keywords
- focus on response codes and repeated patterns
- follow the attacker's IP address across the logs

For example:
- repeated `401` responses suggested failed login attempts
- a later `200` response suggested successful authentication
- user-agent strings clearly revealed tools like Hydra and sqlmap
- FTP logs showed anonymous access and successful file downloads
- auth logs confirmed shell access through SSH

## Simple attack timeline
1. The attacker scanned the target and performed reconnaissance.
2. They explored endpoints and looked for weak points.
3. They used brute force against the login endpoint.
4. They used SQL injection against the product search function.
5. They retrieved sensitive data.
6. They used FTP to access and download files.
7. They later gained shell access through SSH.

## What I learned
This room helped me practise basic SOC thinking in a simple way.

Before this, large logs felt overwhelming. After doing this room, I understood that the goal is not to read everything line by line. The goal is to look for evidence:

- Who did it?
- What did they access?
- Did it fail or succeed?
- What changed after success?

This room helped me get more comfortable with:
- reading log files
- identifying attacker tools
- mapping actions to endpoints
- understanding how web activity can lead to shell access

## Reflection
This was a good beginner exercise because it showed me how much information can be pulled from normal system logs. It also made me more confident about approaching large log files without panicking.
