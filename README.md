# TryHackMe Writeups

**Collection of TryHackMe room write-ups, cheatsheets and small pentest scripts.**  
_Author: Aleksandra Barczyk_

---
## About this repository

This repository documents my practical learning on TryHackMe. It contains detailed write-ups for completed rooms, short cheatsheets I use for daily practice, and small helper scripts (e.g., nmap wrappers). The goal is to build a clear portfolio that shows my progress in web and network security.

**What you will find here**
- Step-by-step write-ups for rooms I completed (with commands and screenshots).  
- Practical cheatsheets for commands and workflows (Linux, networking, web).  
- Small scripts and helpers used during labs (simple, well-commented).  

> Note: This repo is for learning and portfolio purposes. I do not publish any sensitive data — only educational artifacts and lab flags.
---

## Repo structure

```
/                       <- this README
completed_rooms.md      <- one-line log of finished rooms (date, room, flag)
neighbour/              <- example room folder
  ├─ README.md          <- room write-up (detailed)
  └─ images/            <- screenshots for the write-up
network-fundamentals/   <- notes about OSI, ARP, DHCP, subnetting
scripts/                <- useful scripts (e.g. nmap wrappers, curl examples)
cheatsheets/            <- short references (common commands, flags)
```

---
## How I add a write-up

1. Create a folder named after the room: `room-name/`.
2. Inside the folder add `README.md` containing:
   - Objective
   - Steps (step-by-step, exact commands you ran)
   - Evidence (screenshots + optional output snippets)
   - Final flag (if lab)
   - Lessons learned / remediation suggestions
3. Put screenshots into an `images/` subfolder and reference them in the README.
4. Update `completed_rooms.md` with a one-line summary: `YYYY-MM-DD | Room | Difficulty | Flag`.
5. Commit changes with a clear message, for example: `docs: add neighbour write-up and screenshots`.
