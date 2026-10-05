# SecLists-on-Linux

SecLists is just a big collection of wordlists, so there are a few ways to get it depending on the distro.

**On Kali** it's in the official repos:

```bash
sudo apt update && sudo apt install seclists
```

It lands in `/usr/share/seclists/`.

**On Arch** it's in the AUR (or the BlackArch repo if you have that enabled):

```bash
yay -S seclists          # AUR helper
# or, with BlackArch repo enabled:
sudo pacman -S seclists
```

Both install to `/usr/share/seclists/` as well.

**Any distro (manual git clone)** works everywhere and gives you the latest version:

```bash
sudo git clone --depth 1 https://github.com/danielmiessler/SecLists.git /usr/share/seclists
```

The `--depth 1` matters because the full history is huge. To update later, run `cd /usr/share/seclists && sudo git pull`.

To check it worked:

```bash
ls /usr/share/seclists
```

You should see folders like `Discovery`, `Fuzzing`, `Passwords`, `Usernames`, and `Web-Shells`. Commonly used lists include `Discovery/Web-Content/common.txt` and `raft-medium-directories.txt` for directory busting, and `Passwords/Leaked-Databases/rockyou.txt.tar.gz` (extract it first).

Plan for roughly 1–2 GB of disk space either way.
