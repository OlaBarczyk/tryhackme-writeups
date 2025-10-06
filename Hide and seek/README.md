# Hide and seek — TryHackMe write-up

**Room:** Hide and seek (Terminal & IDOR)
**Difficulty:** Easy
**Date:** 2025-10-06

***

## 1. Web Hacking (IDOR - Insecure Direct Object Reference)

**Objective:** Find the flag by exploiting an IDOR vulnerability on the profile page.

### Steps Taken:
- Started the target machine and logged in with `guest:guest`.
- Observed the URL format on the profile page (e.g., `/profile.php?user=1`).
- Exploited the IDOR vulnerability by changing the `user` parameter to known identifiers.
- Visited the admin profile at `/profile.php?user=admin`.
- Inspected the "View Page Source" for the admin profile, where the flag was revealed.

### Findings / Flag 1:
**Flag (IDOR):** `flag{66be95c478473d91a5358f2440c7af1f}`

***

## 2. Terminal Hacking (File System Hide & Seek)

**Objective:** Escalate privileges and locate a second flag hidden within the file system and system services.

### Kluczowe Kroki i Polecenia:
- **Escalation:** Used `sudo su` to gain root privileges.
- **Initial Discovery:** Located a suspicious, recently modified file `win_for_specter.txt` in the user's home directory.
- **Time-Based Search:** Used the `find` command to locate files modified after a key date (e.g., `2025-03-07`).
- **Persistence Analysis:** Checked active system services using `systemctl list-unit-files --type=service | grep enabled`.
- **Final Flag Location:** Examined the configuration of a specific service (e.g., `cipher.service` via `systemctl cat`), which contained the flag broken into multiple numbered parts.

### Findings / Flag 2:
**Flaga (Terminalowa):** `THM{y0u_g0t_3v3ryth1ng_d0wn}`

***

## Notes / Lessons Learned

- **IDOR is Common:** Always try manipulating IDs or parameters in requests (e.g., `?user=X`) when testing web applications.
- **File System Auditing:** After gaining access, crucial information is often found by checking recent file modifications (`find -newermt`).
- **Persistence Mechanisms:** Always check services (like `systemd` units) for malicious or unusual configurations.
