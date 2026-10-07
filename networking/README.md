# Networking Notes

## VirtualBox network modes (Kali VM)

Choosing a network mode for a lab VM is a security decision, not just a setting.

| Mode | Internet for the VM? | VM reachable from host/LAN? | Use it for |
|---|---|---|---|
| **NAT** | Yes (through the host) | No (not directly) | Normal Kali use — browsing, updates, downloads |
| **Host-only** | No | Host only, not the LAN/internet | A closed lab: VMs talk to each other and the host, nothing leaks out |
| **Bridged** | Yes | Yes — the VM is a full member of the LAN | Only when you deliberately want the VM on your real network |

**My practice:** NAT for everyday Kali internet access — `ping -c 4 google.com` returned 4/4 packets, 0% packet loss. Host-only when I want a closed cybersecurity lab where Kali and the other lab VMs can talk to each other without exposing the lab to the internet.

Rule of thumb: *know which network your VM is on before you run anything.*

## Study roadmap

- [ ] **OSI model** — 7 layers, what each layer does, where attacks happen
- [ ] **TCP/IP model** — the 4-layer model used in practice, and how it maps to OSI
- [ ] IP addressing & subnetting basics
- [ ] Core protocols: TCP vs UDP, DNS, DHCP, HTTP/HTTPS
- [ ] Lab commands: `ip addr`, `ping`, `ss -tuln`, `traceroute`

Most attacks and defences make sense once you know which layer you're looking at — that's why this comes next after the Linux basics.
