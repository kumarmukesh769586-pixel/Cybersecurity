# Cybersecurity — My Kali Linux Practice & Lab Notes

My cybersecurity learning repository: hands-on practice in my own Kali Linux lab (VirtualBox VM), Linux fundamentals, networking notes, and my Android Termux + Tailscale remote-access setup.

> All practice is done in my own lab environment, for learning only.

## Repository structure

```
Cybersecurity/
├── README.md                  ← you are here
├── kali-linux-practice/       ← Kali lab session notes + screenshot index
├── linux-basics/              ← Linux command notes
├── networking/                ← VirtualBox network modes, OSI / TCP-IP roadmap
└── termux-tailscale/          ← Termux + Tailscale SSH setup guide
```

## Contents

| Folder | What is inside |
|---|---|
| [kali-linux-practice](kali-linux-practice/) | My Kali Linux practice log: system update, lab folder, users & permissions, ping test — with an index of my practice screenshots |
| [linux-basics](linux-basics/) | The 25 basic Linux commands I practice, with what each one does |
| [networking](networking/) | NAT vs Host-only in VirtualBox, and my networking study roadmap (OSI & TCP/IP models) |
| [termux-tailscale](termux-tailscale/) | How I reach my phone's Termux terminal over SSH using Tailscale |

## Key lessons so far

**1. Patch first.** My first `sudo apt update` check showed 1,381 packages waiting to be upgraded. An out-of-date system is the easiest target — updating is lesson one of cybersecurity.

**2. Terminal fluency is the foundation.** Before any security tools, I practiced 25 basic Linux commands until they felt normal — see [linux-basics](linux-basics/). If you can't move around a system, read files, and check who you are and what's running, you can't secure it or investigate it.

**3. Users and permissions matter most.** Creating a second user (`student`) and changing permissions on a `project` folder taught me the principle of least privilege in two commands:
- `chmod 755 project` → owner read/write/execute; group & others read/execute only (`drwxr-xr-x`)
- `chmod 700 project` → owner only; group & others get *no permission*

**4. Your VM's network mode is a security decision.** NAT for a normal internet connection (my `ping -c 4 google.com` returned 4/4, 0% loss); Host-only for a closed lab. Details in [networking](networking/).

**5. Remote access, set up safely.** I reach Termux on my phone over SSH through my private Tailscale network — guide in [termux-tailscale](termux-tailscale/). Real addresses stay private; the guide uses placeholders.

## Roadmap

- [x] Kali Linux lab setup in VirtualBox
- [x] System update & patching habit
- [x] 25 basic Linux commands
- [x] Users, groups & file permissions
- [x] VirtualBox network modes (NAT vs Host-only)
- [x] Termux + Tailscale SSH access
- [ ] OSI model & TCP/IP model — how data actually moves
- [ ] Networking commands deep-dive (`ip`, `ping`, `ss`, `nmap` basics — lab only)

## Practice screenshots

My Kali practice screenshots are indexed in [kali-linux-practice](kali-linux-practice/README.md).
