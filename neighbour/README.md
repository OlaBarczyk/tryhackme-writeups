# Neighbour — TryHackMe write-up
**Room:** Neighbour (IDOR)  
**Difficulty:** Easy  
**Date:** 2025-10-01

## Objective
Find the flag by exploiting an IDOR (insecure direct object reference) on the profile page.
## Steps taken
1. Start the target machine and Start AttackBox.
2. Open AttackBox Firefox and navigate to the Target IP (from the room panel), e.g. `http://10.10.244.148`.
3. Login using the guest account:
   - Username: `guest`
   - Password: `guest`
4. After login, inspect the profile page. Look at the URL and page source.
5. Change the `user` parameter in the URL to enumerate:
   - `/profile.php?user=1`, `/profile.php?user=2`, `/profile.php?user=admin`
6. Inspect "View Page Source" for the admin profile.

## Findings / Flag
When visiting `?user=admin` the page source revealed the flag:

**Flag:** `flag{66be95c478473d91a5358f2440c7af1f}`

## Notes / Lessons learned
- IDOR vulnerabilities allow attackers to access other users' data by changing identifiers in requests.
- Always try manipulating IDs or parameters when testing web apps.
- Keep screenshots in `neighbour/images/` (refer to them in this README).
