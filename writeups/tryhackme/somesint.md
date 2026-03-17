# TryHackMe — SoMeSINT

## Overview
SoMeSINT is a social media OSINT room where I had to investigate a person by following public information across X/Twitter, Reddit, archived pages, and page source.

Compared to OhSINT, this room felt harder because it was not just one clue from one image. I had to keep following clues from one account to another, check archived pages, and sometimes inspect the page source when something was not visible normally.

## What I used
- Google search
- X / Twitter
- Reddit
- Old Reddit
- Wayback Machine
- Browser page source (`Ctrl + U`)
- Basic SpiderFoot understanding

## What I did

### 1. Started from the username
The room gave Thomas Straussman’s handle, so that became the starting point.

From there, I searched for his public accounts and started collecting clues from his profile, posts, and related accounts.

### 2. Investigated Thomas’s social media
By checking Thomas’s X/Twitter account and related posts, I found personal details such as:
- favourite holiday
- birth date
- fiancée’s account
- background image clue

This showed me that even small profile details can become useful clues if you pay attention.

### 3. Pivoted to Francesca’s account
After finding Francesca’s handle, I moved to her profile and looked through her posts and images.

From there, I found clues about:
- vacation location
- family-related information
- pet-related information
- what show she likes to watch

This part helped me understand how one person’s social media can reveal information about other people connected to them.

### 4. Used archived pages
One of the most useful parts of this room was using the Wayback Machine on Reddit pages.

By checking archived versions of posts and profiles, I found information that was not obvious from the live page. This helped me identify Thomas’s coworker and continue the investigation.

This reminded me that even if something is changed or deleted, it may still exist in archived snapshots.

### 5. Checked page source for hidden clues
Some clues were not clearly visible on the normal page, so I used `Ctrl + U` to inspect the source code.

This helped me find hidden details, including a password clue for the next part of the investigation.

This connected well with OhSINT because it showed me again that hidden text on a page is not really hidden if it still exists in the source.

### 6. Understood the role of SpiderFoot
Task 4 was supposed to be done using SpiderFoot for account enumeration.

In the AttackBox, SpiderFoot returned an invalid target type error, so I could not complete that step exactly as shown in the room. Even so, I still understood what the task was trying to teach:
- use the username as the pivot
- understand the account-finding module
- follow the shadowban lead
- inspect the returned data

One thing I liked here was that even though the tool did not work properly, I could still understand the method behind the task.

## What I learned
This room helped me understand social media OSINT in a more practical way.

The main things I learned were:
1. one username can lead to multiple linked accounts
2. social media posts can reveal much more than people realise
3. archived pages can expose information that is no longer visible
4. page source can still reveal hidden clues
5. OSINT is often about patience, careful reading, and following the next useful pivot

## Security takeaways
- Public social media posts can expose more personal information than expected
- Reusing the same username across platforms makes profiling easier
- Photos, captions, and replies can reveal relationships and location details
- Archived pages can preserve information even after it is deleted or changed
- Content hidden on a webpage may still be visible in source code

## My reflection
This room was more detailed than OhSINT and needed more patience, but it helped me understand how social media investigations work step by step.

What stood out to me most was that the investigation came from normal public behaviour, not from hacking. Usernames, posts, replies, archived pages, and page source were enough to build a much bigger picture.

It also reminded me that even when a tool fails, understanding the process still matters.

> Note: This write-up focuses on methodology and lessons learned rather than listing challenge answers directly.
