# Termux + Tailscale — SSH Into My Phone

How I reach the Termux terminal on my Android phone over SSH, from another device, using Tailscale (a private network — my devices only).

> **Security note:** this repo is public, so my real Tailscale IP, Termux username and password are **not** written here. Use your own values where the placeholders `<...>` appear. Never publish real addresses or credentials.

## How it fits together

- **Termux** — a Linux terminal app on Android. It can run an SSH server (`sshd`).
- **Tailscale** — puts my phone and my other device on one private network, each with its own stable private IP (100.x.x.x range). Traffic is end-to-end encrypted.
- **SSH** — the protocol I use to log in to Termux from the other device.

## Details (fill in your own)

| Item | Value |
|---|---|
| Phone Tailscale IP | `<phone-tailscale-ip>` (find it in the Tailscale app) |
| Termux username | `<termux-username>` (run `whoami` in Termux) |
| SSH port | `8022` (Termux default) |

Connect from any device signed in to the **same Tailscale account**:

```bash
ssh -p 8022 <termux-username>@<phone-tailscale-ip>
```

## One-time setup (in Termux)

```bash
pkg update && pkg install openssh
passwd        # set the password you will enter when connecting
sshd          # start the SSH server
```

## Connect again — 3 steps every time

1. **Phone:** open Tailscale and turn it **ON** (VPN active).
2. **Phone, in Termux:** run `sshd` — the server does not stay running after Termux closes or the phone restarts.
3. **Other device** (Tailscale ON, same account): run the SSH command above and enter the Termux password.

Type `exit` to close the session. Turn Tailscale off on the phone when done if you don't want to stay on the VPN — Android allows only one VPN at a time.

## Yazi file manager (in Termux)

- Start it with **`yazi`** — not `ya` (`ya` is only the plugin helper, e.g. `ya pkg add ...`).
- Open straight in shared storage: `yazi ~/storage/shared`
- Keys: arrow keys / `h j k l` move, `Enter` or `l` open, `q` quit.

## Troubleshooting

| Problem | Check |
|---|---|
| Connection timed out | Is Tailscale ON on **both** devices, same account? |
| Connection refused | Is `sshd` running in Termux? Run it again. |
| Wrong password | The password is the one set with `passwd` in Termux, not your phone PIN. |
| IP looks different | Tailscale IPs are stable per device, but confirm in the Tailscale app. |
