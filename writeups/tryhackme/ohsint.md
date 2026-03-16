# TryHackMe — OhSINT

## Overview
OhSINT is a beginner-friendly OSINT room that shows how much information can be found from just one image.

At the start, I only had one image file. From that image, I extracted metadata, found a username, and then used that clue to connect information across public websites like social media, GitHub, and a blog.

What I liked about this room is that it was not about hacking into anything. It was about thinking carefully, following clues, and building a profile from public information.

## What I used
- `exiftool`
- Google search
- GitHub
- X / Twitter
- Blog page source (`Ctrl + U`)

## What I did

### 1. Checked the image metadata
I started by using `exiftool` on the image.

This gave me two important clues:
- GPS coordinates
- a username/copyright value

That showed me straight away that images can leak useful information if metadata is left inside.

### 2. Searched the username
I searched the username online and found linked public profiles.

This helped me connect the person’s:
- avatar
- city
- email address
- social media presence
- personal blog

This part taught me how useful username reuse can be in OSINT investigations.

### 3. Looked at social media clues
From the social media profile, I found extra details including a wireless access point clue.

This was a good reminder that people sometimes post technical details online without realising they can reveal more information than intended.

### 4. Checked GitHub
The GitHub profile helped confirm more personal details, including contact information and location.

This showed how developer profiles can expose:
- public email addresses
- location details
- linked identities across different sites

### 5. Viewed the website source code
The final clue came from checking the blog page source.

The page itself looked normal, but the source contained hidden text inside the blog content. This reinforced an important lesson: information hidden visually on a webpage is still visible in the source.

## What I learned
This room helped me practise a simple OSINT process:

1. extract clues  
2. identify a useful pivot  
3. search across public sources  
4. connect the information  
5. verify before answering  

The biggest lesson for me was how easily small public details can be combined into a bigger picture.

## Security takeaways
- Image metadata should be removed before sharing publicly when privacy matters.
- Reusing the same username across platforms makes profiling easier.
- Public GitHub profiles can leak more personal information than expected.
- Small technical details shared online can become useful OSINT clues.
- Hidden webpage content is not really hidden if someone checks the source code.

## My reflection
This room was a good introduction to OSINT because it was simple but still made me think carefully.

It taught me that investigation is not about guessing. It is about noticing one clue, following it properly, and checking whether the next piece of information makes sense.

It also made me more aware of how normal online behaviour can expose personal information without the person realising it.

> Note: This write-up focuses on methodology and lessons learned rather than listing challenge answers directly.
