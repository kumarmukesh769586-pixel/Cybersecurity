# Kali Linux Practice — Lab Log

Hands-on practice in my own Kali Linux VM (VirtualBox). Everything here is done in my private lab, for learning.

## Session log

1. **System update** — Ran `sudo apt update`; 1,381 packages were waiting to be upgraded. Lesson: *patch first* — an out-of-date system is the easiest target.
2. **Basic commands practice** — Worked through 25 basic Linux commands (full list in [../linux-basics](../linux-basics/)).
3. **Files and folders** — Created a `test` folder and `file.txt` ("Hello Kali"), then a dedicated `~/cyberlab` lab folder with `test.txt` ("Kali Linux Lab"). Keeping practice in one lab folder keeps experiments tidy and easy to delete.
4. **Users** — Created a second user, `student` (`sudo adduser student`), to practice working with more than one account.
5. **Permissions** — Practised on a `project` folder:
   - `chmod 755 project` → `drwxr-xr-x` (owner: rwx, group/others: r-x)
   - `chmod 700 project` → owner only, nobody else gets anything
   - Also learned the funny way that `Owner`, `Group` and `Others` are *concepts, not commands* — typing them into the terminal gives "command not found".
6. **Networking check** — `ping -c 4 google.com` returned 4/4 packets, 0% loss on NAT. Network-mode notes are in [../networking](../networking/).

## Screenshot index

Practice screenshots (currently stored at the repository root):

| File | What it shows |
|---|---|
| `1Image` | Kali Linux practice screenshot |
| `2 Image` | Kali Linux practice screenshot |
| `WhatsApp Image 2026-10-04 at 6.22.08 PM.jpeg` | Kali practice — desktop / terminal session |
| `WhatsApp Image 2026-10-04 at 6.22.19 PM.jpeg` | Kali practice — terminal session |
| `WhatsApp Image 2026-10-04 at 6.22.28 PM.jpeg` | Kali practice — terminal session |
| `WhatsApp Image 2026-10-04 at 6.23.25 PM.jpeg` and `(1)`, `(2)` variants | Kali practice — commands / files session |
| `WhatsApp Image 2026-10-04 at 6.23.26 PM.jpeg` and `(1)`–`(7)` variants | Kali practice — users, permissions and lab-folder session |
| `WhatsApp Image 2026-10-04 at 6.23.28 PM.jpeg` and `(1)`–`(3)` variants | Kali practice — networking / ping session |

Topics covered across the screenshots: `apt update` and the upgrade list, basic Linux commands, the `~/cyberlab` folder, creating the `student` user, `chmod 755` vs `chmod 700`, VirtualBox network adapter settings, and the `ping` connectivity test.

## Next practice

- OSI model & TCP/IP model notes
- Networking commands: `ip addr`, `ss -tuln`, basic `nmap` scan of my own lab VM only
