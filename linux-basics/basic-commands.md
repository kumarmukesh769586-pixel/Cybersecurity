# 25 Basic Linux Commands

The first commands I practiced in my Kali lab until they felt normal.

| # | Command | What it does |
|---|---|---|
| 1 | `pwd` | Show the current directory |
| 2 | `ls -la` | List all files (including hidden) with details |
| 3 | `cd <dir>` | Change directory |
| 4 | `mkdir <dir>` | Create a folder |
| 5 | `touch <file>` | Create an empty file |
| 6 | `cp <src> <dst>` | Copy a file |
| 7 | `mv <src> <dst>` | Move or rename a file |
| 8 | `rm <file>` | Delete a file (careful — no recycle bin) |
| 9 | `cat <file>` | Print a file's contents |
| 10 | `echo "text"` | Print text (or write it into a file with `>`) |
| 11 | `nano <file>` | Edit a file in the nano editor |
| 12 | `head <file>` | Show the first lines of a file |
| 13 | `tail <file>` | Show the last lines of a file |
| 14 | `grep <word> <file>` | Search for text inside a file |
| 15 | `find <dir> -name <file>` | Find files by name |
| 16 | `whoami` | Show the current user |
| 17 | `hostname` | Show the machine's name |
| 18 | `id` | Show user ID and group IDs |
| 19 | `ip addr` | Show network interfaces and IP addresses |
| 20 | `ping -c 4 <host>` | Test connectivity (4 packets) |
| 21 | `ps` | Show running processes |
| 22 | `df -h` | Show disk space, human-readable |
| 23 | `free -h` | Show RAM usage, human-readable |
| 24 | `uname -a` | Show kernel and system information |
| 25 | `chmod <mode> <file>` | Change file permissions (e.g. `755`, `700`) |

## Why these come first

If you can't move around a system, read files, and check who you are and what's running, you can't secure it — or investigate it. These 25 are the foundation everything else is built on.

See also: [../kali-linux-practice](../kali-linux-practice/) for how I used them in the lab.
