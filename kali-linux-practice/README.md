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
7. **OSI model notes** — Wrote the 7-layer OSI model into `osi.txt` with an example and a mnemonic for each layer.
8. **System info script (Python)** — Wrote a small `system_info.py` using `socket`, `platform` and `uuid` to print hostname, IP address, MAC address, OS and Python version. Lesson learned: Python code goes in a *file* — pasting it straight into zsh gives `parse error`.
9. **System report** — Collected CPU details with `lscpu` (Intel i7-8850H, 12 CPUs), plus `free -h`, `df -h`, `ip addr` and `ip route` for a full system report.
10. **Wireshark** — Opened Wireshark 4.6.6 and reviewed the capture interfaces (`wlan0`, `eth0`, loopback).
11. **Burp Suite + troubleshooting** — Hit a Java version error launching Burp Suite (`UnsupportedClassVersionError` — Burp needs a newer Java than the runtime default), then ran the standard connectivity checks: `ping -c 4 8.8.8.8` and `ping -c 4 google.com`, both 0% loss.
12. **Interfaces & psutil** — Inspected interfaces with `ip link`, brought `eth0` up with `sudo ip link set eth0 up`, and tried a `psutil` CPU/RAM usage snippet in Python (more zsh parse errors — same lesson as #8: use a file or the Python REPL).

## Screenshot index

All practice screenshots live in this folder, in session order:

| File | What it shows |
|---|---|
| `01-kali-desktop.jpg` | Kali Linux desktop |
| `02-apt-update-upgradable-packages.jpg` | `sudo apt update` — 1,381 upgradable packages |
| `03-upgradable-packages-continued.jpg` | Upgradable package list (b–c) |
| `04-upgradable-packages-g-l.jpg` | Upgradable package list (g–l) |
| `05-upgradable-packages-l-s.jpg` | Upgradable package list (l–s) |
| `06-practicing-linux-commands.jpg` | Practising basic Linux commands (`pwd`, `ls -la`, `mkdir`, `touch`, …) |
| `07-nano-file-edit.jpg` | Editing `file.txt` in nano — "Hello Kali" |
| `08-cyberlab-folder.jpg` | Creating the `~/cyberlab` lab folder |
| `09-user-and-permissions.jpg` | `adduser student`, `chmod 755` vs `chmod 700` |
| `10-ping-and-network.jpg` | `ping` test + VirtualBox network notes |
| `11-osi-model-notes.jpg` | OSI model notes in `osi.txt` |
| `12-system-info-python-script.jpg` | Writing the `system_info.py` Python script |
| `13-lscpu-cpu-info.jpg` | `lscpu` — CPU details (i7-8850H, 12 CPUs) |
| `14-system-report-details.jpg` | System report — vulnerabilities, `free -h`, `df -h`, `ip addr`, routes |
| `15-wireshark.jpg` | Wireshark 4.6.6 — capture interface list |
| `16-burpsuite-error-and-ping-tests.jpg` | Burp Suite Java error + `ping` connectivity tests |
| `17-ip-link-interface-up.jpg` | `ip link`, bringing `eth0` up, `apt update` re-check |
| `18-psutil-cpu-ram-attempt.jpg` | Installing `python3-psutil`, first CPU/RAM snippet attempt |
| `19-psutil-and-system-info-output.jpg` | psutil attempt + `system_info.py` output and errors |

## Next practice

- Networking commands: `ip addr`, `ss -tuln`, basic `nmap` scan of my own lab VM only
- Fix the Burp Suite Java version and launch it successfully
- Run `system_info.py` from a file (not pasted into zsh) and save the output
