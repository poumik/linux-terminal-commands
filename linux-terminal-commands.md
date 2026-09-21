# Linux Terminal Reference — 300+ Commands, Concepts & Recipes

A practical Linux terminal reference for sysadmins, developers, and advanced users.

This file is the canonical reference. The README is intentionally shorter and links back to this document.

## Legend

- 🟢 **Safe** — normally read-only or low-risk.
- 🟡 **Caution** — changes state/configuration but is usually recoverable.
- 🔴 **Destructive** — can delete, overwrite, repartition, or seriously damage data.
- 🔐 **sudo** — commonly requires elevated privileges.
- 🌍 **Not universal** — distro/package-dependent.
- 💡 **Tip** — useful shortcut or best practice.

> **Before running an unfamiliar command:** try `command --help`, then `man command`.
> Availability and exact options can vary by distro, shell, and installed packages.

## Table of contents

1. [Command Discovery & Help](#1-command-discovery--help)
2. [Files & Directory Management](#2-files--directory-management)
3. [Viewing & Editing Files](#3-viewing--editing-files)
4. [Text Processing & Data Transformation](#4-text-processing--data-transformation)
5. [Pipelines & Redirection](#5-pipelines--redirection)
6. [Permissions & Ownership](#6-permissions--ownership)
7. [Users & Groups](#7-users--groups)
8. [Processes & Job Control](#8-processes--job-control)
9. [System & Performance Monitoring](#9-system--performance-monitoring)
10. [Storage & Filesystems](#10-storage--filesystems)
11. [Networking Diagnostics & Transfer](#11-networking-diagnostics--transfer)
12. [Archives & Compression](#12-archives--compression)
13. [Shell Environment & Builtins](#13-shell-environment--builtins)
14. [Shell Scripting Basics](#14-shell-scripting-basics)
15. [Shell Shortcuts, History & Globbing](#15-shell-shortcuts-history--globbing)
16. [systemd, Services & Logs](#16-systemd-services--logs)
17. [Package Managers](#17-package-managers)
18. [Hardware & Kernel Inspection](#18-hardware--kernel-inspection)
19. [Executables, Libraries & Binary Inspection](#19-executables-libraries--binary-inspection)
20. [Checksums & Integrity](#20-checksums--integrity)
21. [Version Control & Development Utilities](#21-version-control--development-utilities)
22. [Terminal Multiplexing & Modern Replacements](#22-terminal-multiplexing--modern-replacements)
23. [Practical Troubleshooting Workflow](#23-practical-troubleshooting-workflow)
24. [Practical Recipes](#24-practical-recipes)
25. [Security & Safety Rules](#25-security--safety-rules)
26. [Aliases & Functions](#26-aliases--functions)
27. [Make It Yours](#27-make-it-yours)
28. [Terminal Fun & Eye Candy](#28-terminal-fun--eye-candy)
29. [Quick Safety Summary](#29-quick-safety-summary)
30. [Final Rule](#30-final-rule)

---

# 1. Command Discovery & Help

| # | Command | Description |
|---|---|---|
| 1 | `man` | Read the manual page for a command. |
| 2 | `info` | Read GNU Info documentation where available. |
| 3 | `help` | Show help for Bash builtins. |
| 4 | `apropos` | Search manual-page descriptions by keyword. |
| 5 | `whatis` | Show a one-line command description. |
| 6 | `type` | Show how the shell interprets a command. |
| 7 | `which` | Show the path of an executable; `command -v` is generally more portable for shell scripts. |
| 8 | `command -v` | Check how the shell resolves a command. |
| 9 | `whereis` | Locate binary, source, and manual-page files. |

Examples:

```bash
command --help
man command
apropos network
command -v python
type cd
```

---

# 2. Files & Directory Management

| # | Command | Description |
|---|---|---|
| 10 | `ls` | List directory contents (`-la` for detailed/all entries). |
| 11 | `cd` | Change directory. |
| 12 | `pwd` | Print current working directory. |
| 13 | `mkdir` | Create directories (`-p` creates parents). |
| 14 | `rmdir` | Remove an empty directory. |
| 15 | `rm` | Remove files/directories. 🔴 |
| 16 | `cp` | Copy files/directories. 🟡 |
| 17 | `mv` | Move or rename files/directories. 🟡 |
| 18 | `touch` | Create a file or update timestamps. |
| 19 | `ln` | Create hard or symbolic links. |
| 20 | `find` | Search for files/directories by many criteria. |
| 21 | `locate` | Fast filename search using a database. |
| 22 | `tree` | Display a directory tree. |
| 23 | `stat` | Display detailed file metadata. |
| 24 | `file` | Identify a file's type/content. |
| 25 | `realpath` | Resolve a canonical absolute path. |
| 26 | `readlink` | Inspect symbolic links; `-f` resolves a path. |
| 27 | `basename` | Extract the final filename component. |
| 28 | `dirname` | Extract the directory component. |
| 29 | `install` | Copy files while setting permissions/ownership. |
| 30 | `mktemp` | Create a unique temporary file/directory safely. |
| 31 | `truncate` | Resize or create a file to a specified size; shrinking discards data. 🔴 |

💡 Preview a glob before a destructive command:

```bash
printf '%s\n' ./*.log
rm -- ./*.log
```

⚠️ `cp`, `mv`, `>`, and `tee` can overwrite files silently unless you guard against it. Use `cp -n`, `cp -i`, `mv -n`, `mv -i`, or `set -o noclobber` when you want explicit protection. `truncate -s 0 file` also discards a file's contents immediately.

---

# 3. Viewing & Editing Files

| # | Command | Description |
|---|---|---|
| 32 | `cat` | Print/concatenate files. |
| 33 | `less` | Scroll through files; search with `/pattern`. |
| 34 | `more` | Older pager; `less` is usually preferable. |
| 35 | `head` | Show the beginning of a file. |
| 36 | `tail` | Show the end; `-f` follows a changing file. |
| 37 | `nano` | Beginner-friendly terminal editor. |
| 38 | `vim` | Powerful modal editor. |
| 39 | `tac` | Print file lines in reverse order. |
| 40 | `rev` | Reverse characters on each line. |

---

# 4. Text Processing & Data Transformation

| # | Command | Description |
|---|---|---|
| 41 | `grep` | Search text using patterns/regex. |
| 42 | `sed` | Stream editor for substitutions, deletion, and transformation. |
| 43 | `awk` | Pattern scanning and structured text processing. |
| 44 | `cut` | Extract fields/columns. |
| 45 | `tr` | Translate, squeeze, or delete characters. |
| 46 | `sort` | Sort lines. |
| 47 | `uniq` | Remove/report adjacent duplicate lines. |
| 48 | `wc` | Count lines, words, bytes, and characters. |
| 49 | `diff` | Compare files line by line. |
| 50 | `patch` | Apply a diff/patch. |
| 51 | `tee` | Copy stdin to stdout and a file. |
| 52 | `xargs` | Build commands from stdin. |
| 53 | `column` | Align tabular text. |
| 54 | `paste` | Merge files line-by-line. |
| 55 | `join` | Join sorted files on a common field. |
| 56 | `comm` | Compare two sorted files. |
| 57 | `nl` | Number lines. |
| 58 | `fold` | Wrap long lines. |
| 59 | `expand` | Convert tabs to spaces. |
| 60 | `unexpand` | Convert spaces to tabs. |
| 61 | `seq` | Generate numeric sequences. |
| 62 | `split` | Split a file into pieces. |
| 63 | `csplit` | Split a file at pattern/context boundaries. |
| 64 | `jq` | Parse and transform JSON. |
| 65 | `base64` | Encode/decode Base64 data. |
| 66 | `iconv` | Convert text between character encodings. |
| 67 | `cmp` | Compare two files byte by byte. |

Useful examples:

```bash
grep -r --include="*.py" "function_name" .
grep -C 5 "error" log.txt
cut -d: -f1 /etc/passwd
find . -maxdepth 1 -name '*.log' | sort
jq '.users[] | .name' data.json
```

---

# 5. Pipelines & Redirection

These are shell operators rather than standalone commands, but they are fundamental terminal skills.

| Syntax | Meaning |
|---|---|
| `>` | Redirect stdout, replacing the destination file. |
| `>>` | Append stdout to a file. |
| `<` | Read stdin from a file. |
| `2>` | Redirect stderr. |
| `2>>` | Append stderr. |
| `2>&1` | Send stderr to the same destination as stdout. |
| `\|` | Pipe stdout into another command's stdin. |
| `\|&` | Pipe stdout and stderr together in Bash. |
| `tee` | View output while writing it to a file. |
| `$(command)` | Command substitution. |
| `<(command)` | Process substitution in Bash/Zsh. |
| `<<EOF` | Here-document: feed multiline text to a command. |

Examples:

```bash
command > output.txt
command >> output.txt
command 2> errors.txt
command >output.txt 2>&1
command | grep error
command |& tee output.log

name=$(whoami)

cat <<EOF
Hello $USER
This is a multiline block.
EOF
```

---

# 6. Permissions & Ownership

| # | Command | Description |
|---|---|---|
| 68 | `chmod` | Change permissions. 🟡 |
| 69 | `chown` | Change owner/group. 🔐 |
| 70 | `chgrp` | Change group ownership. 🔐 |
| 71 | `umask` | Control default permissions for new files. |
| 72 | `sudo` | Execute a command with elevated/another-user privileges. 🔐 |
| 73 | `su` | Switch user. 🔐 |
| 74 | `groups` | Show group memberships. |
| 75 | `id` | Show UID/GID and group information. |
| 76 | `getfacl` | View POSIX ACLs. |
| 77 | `setfacl` | Set POSIX ACLs. |
| 78 | `chattr` | Change filesystem attributes such as immutable. 🔐 |
| 79 | `lsattr` | List filesystem attributes. |
| 80 | `passwd` | Change a user's password. |
| 81 | `chage` | Manage password aging/expiry. |

### Permission basics

```text
r = 4
w = 2
x = 1

755 = rwxr-xr-x
644 = rw-r--r--
700 = rwx------
```

Symbolic examples:

```bash
chmod u+x script.sh
chmod go-r secret.txt
chmod 640 config.ini
```

ACL example:

```bash
getfacl file.txt
setfacl -m u:alice:r file.txt
```

---

# 7. Users & Groups

| # | Command | Description |
|---|---|---|
| 82 | `whoami` | Print current effective username. |
| 83 | `who` | Show logged-in users. |
| 84 | `w` | Show users and what they are doing. |
| 85 | `last` | Show login history. |
| 86 | `useradd` | Create a user. 🔐 |
| 87 | `usermod` | Modify a user. 🔐 |
| 88 | `userdel` | Delete a user. 🔴🔐 |
| 89 | `groupadd` | Create a group. 🔐 |
| 90 | `groupdel` | Delete a group. 🔴🔐 |
| 91 | `newgrp` | Temporarily switch effective group. |
| 92 | `chsh` | Change a user's login shell. 🟡 |
| 93 | `chfn` | Change a user's GECOS/finger information. 🟡 |

💡 Example: add a user to an extra group while keeping existing groups:

```bash
sudo usermod -aG developers alice
```

⚠️ Omitting `-a` removes the user from all other groups that are not explicitly listed; use it carefully.

⚠️ Some groups are effectively privileged: membership in `docker` is roughly equivalent to root access, and `sudo` / `wheel` grants administrative rights. Add users only to groups they need.

---

# 8. Processes & Job Control

| # | Command | Description |
|---|---|---|
| 94 | `ps` | Snapshot of processes. |
| 95 | `top` | Interactive process/resource monitor. |
| 96 | `htop` | Improved interactive process monitor. 🌍 |
| 97 | `btop` | Modern interactive resource monitor. 🌍 |
| 98 | `pgrep` | Find PIDs by process name/pattern. |
| 99 | `pkill` | Send signals to matching processes. 🟡 |
| 100 | `kill` | Send a signal to a PID. 🟡 |
| 101 | `killall` | Signal processes by name. 🟡 |
| 102 | `pstree` | Display process parent/child relationships. |
| 103 | `jobs` | List shell background jobs. |
| 104 | `bg` | Resume a suspended job in background. |
| 105 | `fg` | Bring a job to the foreground. |
| 106 | `nohup` | Keep a process running after terminal hangup. |
| 107 | `disown` | Remove a job from shell job control. |
| 108 | `timeout` | Stop a command after a time limit. |
| 109 | `nice` | Start a process with adjusted priority. |
| 110 | `renice` | Change an existing process's priority. |
| 111 | `wait` | Wait for background processes. |
| 112 | `pidof` | Find PIDs by executable name. |

💡 Prefer graceful termination first:

```bash
kill PID
# Wait a few seconds and check status
ps -p PID
# If it is still stuck:
kill -KILL PID
```

`kill` sends `SIGTERM` by default, so `kill -TERM PID` is usually the same as `kill PID`.

---

# 9. System & Performance Monitoring

| # | Command | Description |
|---|---|---|
| 113 | `uptime` | Show uptime and load average. |
| 114 | `free` | Show RAM/swap usage. |
| 115 | `df` | Show filesystem free space. |
| 116 | `du` | Estimate directory/file disk usage. |
| 117 | `vmstat` | Show memory, paging, process, and CPU statistics. |
| 118 | `iostat` | CPU and disk I/O statistics. 🌍 |
| 119 | `sar` | Historical system activity data. 🌍 |
| 120 | `iotop` | Per-process disk I/O monitor. 🌍🔐 |
| 121 | `lsof` | List open files, processes, and sockets. |
| 122 | `fuser` | Identify processes using files/sockets. |
| 123 | `strace` | Trace system calls/signals. |
| 124 | `ltrace` | Trace library calls. 🌍 |
| 125 | `perf` | Linux performance/profiling toolkit. 🌍 |
| 126 | `watch` | Re-run a command periodically. |
| 127 | `time` | Measure command execution time. |

---

# 10. Storage & Filesystems

| # | Command | Description |
|---|---|---|
| 128 | `lsblk` | List block devices and partitions. |
| 129 | `blkid` | Show filesystem UUID/type information. |
| 130 | `findmnt` | Inspect mounted filesystems. |
| 131 | `mount` | Mount a filesystem. 🔐 |
| 132 | `umount` | Unmount a filesystem. 🔐 |
| 133 | `fdisk` | Partition-table editor. 🔴🔐 |
| 134 | `mkfs` | Create a filesystem. 🔴🔐 |
| 135 | `fsck` | Check/repair filesystems. 🔴🔐 |
| 136 | `e2fsck` | Check/repair ext2/3/4 filesystems. 🔴🔐 |
| 137 | `tune2fs` | Tune ext2/3/4 filesystem parameters. 🔐 |
| 138 | `dd` | Low-level byte-for-byte copying/conversion. 🔴🔐 |
| 139 | `sync` | Flush filesystem buffers. |
| 140 | `ncdu` | Interactive disk-usage browser. 🌍 |
| 141 | `parted` | Partition disks and resize partitions. 🔴🔐 |
| 142 | `smartctl` | Read SMART health and diagnostics for drives. 🔐 |
| 143 | `lvm` | Manage LVM volumes, groups, and snapshots. 🟡🔐 |
| 144 | `swapon` | Enable swap devices/files. 🔐 |
| 145 | `shred` | Overwrite a file repeatedly before deletion. 🔴 |

⚠️ `dd`, `mkfs`, partitioning tools, and filesystem repair commands can destroy data if pointed at the wrong device.

⚠️ `shred` is not reliable for every filesystem or storage device, especially SSDs and copy-on-write filesystems. Full-disk encryption and device-specific secure-erase tools are often more appropriate.

💡 Read-only LVM inspection tools such as `pvs`, `vgs`, and `lvs` are usually safe. Create/remove operations such as `lvcreate`, `lvremove`, `vgremove`, and `pvremove` are destructive and should be treated with caution.

---

# 11. Networking Diagnostics & Transfer

| # | Command | Description |
|---|---|---|
| 146 | `ip` | Inspect/manage interfaces, addresses, and routes. |
| 147 | `ss` | Inspect sockets/listening ports. |
| 148 | `ping` | Test IP connectivity with ICMP. |
| 149 | `traceroute` | Trace network paths. 🌍 |
| 150 | `mtr` | Interactive ping + traceroute. 🌍 |
| 151 | `dig` | Detailed DNS queries. 🌍 |
| 152 | `nslookup` | DNS queries. 🌍 |
| 153 | `host` | Simple DNS lookup. 🌍 |
| 154 | `curl` | Transfer/test HTTP and other protocols. |
| 155 | `wget` | Download files non-interactively. |
| 156 | `ssh` | Secure remote shell. |
| 157 | `scp` | Copy files over SSH. |
| 158 | `rsync` | Efficient remote or local file sync and transfer. 🟡 |
| 159 | `sftp` | Interactive file transfer over SSH. |
| 160 | `ssh-keygen` | Generate/manage SSH keys. |
| 161 | `ssh-agent` | Cache SSH private-key credentials. |
| 162 | `nc` | Read/write TCP/UDP connections. 🌍 |
| 163 | `openssl` | TLS, certificates, hashes, and crypto utilities. |
| 164 | `ethtool` | Inspect/configure Ethernet interface capabilities. 🔐🌍 |
| 165 | `nmcli` | Manage NetworkManager from the CLI. 🌍 |
| 166 | `resolvectl` | Inspect/test systemd-resolved DNS. 🌍 |
| 167 | `getent` | Query NSS databases such as users, groups, and hosts. |
| 168 | `nmap` | Network discovery and port scanning. 🌍 |
| 169 | `tcpdump` | Capture packets on an interface. 🌍🔐 |
| 170 | `ufw` | Manage the Uncomplicated Firewall. 🟡🌍🔐 |
| 171 | `nft` | Manage nftables firewall rules. 🟡🌍🔐 |
| 172 | `iptables` | Legacy packet filter firewall rules. 🟡🌍🔐 |
| 173 | `firewall-cmd` | Manage firewalld rules. 🟡🌍🔐 |
| 174 | `whois` | Look up domain/IP registration information. 🌍 |
| 175 | `iftop` | Per-connection network bandwidth monitor. 🌍🔐 |
| 176 | `nethogs` | Per-process network bandwidth monitor. 🌍🔐 |
| 177 | `lftp` | Scriptable FTP/HTTP/SFTP client. 🌍 |

Examples:

```bash
ip addr
ip route
ss -tuln
dig example.com
curl -I https://example.com
lsof -i :8080
```

💡 `netstat` and `ifconfig` are legacy; prefer `ss`, `ip`, and `ip addr` / `ip route`.

⚠️ Only scan networks, hosts, or traffic you are authorized to test or capture.

⚠️ Firewall changes (`ufw`, `nft`, `iptables`, `firewall-cmd`) can lock you out of a remote machine. Allow SSH before enabling default-deny rules, and keep a second session open while testing.

---

# 12. Archives & Compression

| # | Command | Description |
|---|---|---|
| 178 | `tar` | Create/list/extract tar archives. |
| 179 | `gzip` | Compress/decompress gzip data. |
| 180 | `gunzip` | Decompress gzip files. |
| 181 | `bzip2` | Compress/decompress bzip2 data. |
| 182 | `xz` | High-ratio compression. |
| 183 | `zstd` | Fast modern compression. 🌍 |
| 184 | `zip` | Create ZIP archives. |
| 185 | `unzip` | Extract/list ZIP archives. |
| 186 | `7z` | 7-Zip archive utility. 🌍 |
| 187 | `zcat` | Read gzip-compressed files. |
| 188 | `zgrep` | Search inside compressed files. |
| 189 | `zless` | Page through compressed files. |

Useful `tar` patterns:

```bash
# List without extracting
tar -tf archive.tar
tar -tzf archive.tar.gz

# Extract
tar -xf archive.tar
tar -xzf archive.tar.gz

# Extract into a chosen directory
tar -xzf archive.tar.gz -C ./destination

# Create
tar -czf backup.tar.gz ./project
```

💡 GNU `tar` auto-detects compression on extract, so `tar -xf` often works for `.tar.gz`, `.tar.xz`, and `.tar.zst` without explicitly specifying `-z`/`-J`/`--zstd`.

💡 Before extracting an untrusted archive, inspect its contents with `tar -tf` / `unzip -l`. Be cautious of archives containing absolute paths or `../` traversal entries.

---

# 13. Shell Environment & Builtins

| # | Command | Description |
|---|---|---|
| 190 | `echo` | Print text/variables. |
| 191 | `printf` | Predictable formatted output; preferred over `echo` in many scripts. |
| 192 | `export` | Export environment variables to child processes. |
| 193 | `env` | Display/run commands with environment settings. |
| 194 | `printenv` | Print environment variables. |
| 195 | `set` | Show/set shell variables and options. |
| 196 | `unset` | Remove shell variables/functions. |
| 197 | `source` / `.` | Execute a script in the current shell. |
| 198 | `exec` | Replace the current shell process with a command. |
| 199 | `read` | Read input into variables. |
| 200 | `shift` | Shift positional parameters. |
| 201 | `getopts` | Parse shell-script options. |
| 202 | `trap` | Run actions when signals/events occur. |
| 203 | `ulimit` | View/set shell resource limits. |
| 204 | `exit` | Exit a shell/script with a status. |
| 205 | `logout` | Log out of a login shell. |
| 206 | `clear` | Clear the terminal display. |
| 207 | `history` | Show shell command history. |
| 208 | `alias` | Define command shortcuts. |
| 209 | `sleep` | Pause execution. |
| 210 | `yes` | Repeatedly output text. |
| 211 | `fc` | List/edit/re-run previous commands. |
| 212 | `bind` | Configure/readline key bindings in Bash. |
| 213 | `test` / `[` | Evaluate conditional expressions. |
| 214 | `tput` | Query terminal capabilities. |
| 215 | `bc` | Arbitrary-precision calculator language. |
| 216 | `script` | Record a terminal session to a file. 🟡 |

⚠️ `script` logs everything displayed in the session, including any tokens, keys, or passwords shown on screen. Do not share the log without reviewing it.

---

# 14. Shell Scripting Basics

These examples assume Bash syntax (`[[ ... ]]`, `pipefail`, and common Bash builtins). They are not POSIX `sh`-portable.

```bash
#!/usr/bin/env bash
```

## Variables

```bash
name="Linux"
echo "$name"
```

No spaces around `=`.

## Quoting

```bash
"$file"       # Preserve spaces and most special characters
'$file'       # Literal text; no variable expansion
"$@"          # Preserve every positional argument separately
```

Prefer quoting variables unless you specifically need shell word splitting/globbing.

## Exit codes

```bash
command
echo $?
```

- `0` normally means success.
- Non-zero means failure or another condition.

## Arguments

```bash
$0      # Script name
$1      # First argument
$2      # Second argument
$#      # Number of arguments
$@      # Positional arguments
"$@"    # Each argument preserved as a separate word
```

For forwarding arguments, prefer:

```bash
some_command "$@"
```

## Conditions

```bash
if [[ -f "$file" ]]; then
    echo "File exists"
else
    echo "Missing"
fi
```

## Loops

```bash
for file in *.log; do
    echo "$file"
done

while read -r line; do
    echo "$line"
done < input.txt
```

## Functions

```bash
greet() {
    printf 'Hello, %s\n' "$1"
}

greet "world"
```

## Safer Bash defaults

```bash
set -euo pipefail
```

Understand what each option does before applying it blindly: `-e` has important edge cases, while `-u` can expose unset-variable assumptions, and `pipefail` changes pipeline status behavior.

---

# 15. Shell Shortcuts, History & Globbing

### Keyboard shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl+A` | Beginning of line. |
| `Ctrl+E` | End of line. |
| `Alt+B` / `Alt+F` | Move one word. |
| `Ctrl+U` | Delete before cursor. |
| `Ctrl+K` | Delete after cursor. |
| `Ctrl+W` | Delete previous word. |
| `Ctrl+R` | Search command history. |
| `Ctrl+L` | Clear screen. |
| `Ctrl+D` | Exit/EOF. |
| `Ctrl+Z` | Suspend current process. |
| `Ctrl+_` | Undo shell-line editing. |
| `Ctrl+X Ctrl+E` | Edit current command in `$EDITOR`. |

### History expansion

```bash
!!
!$
!^
!string
```

⚠️ Review history expansions before executing commands that modify/delete data.

### Globbing and brace expansion

```bash
*.log
file?.txt
{a,b,c}
{1..10}
```

Bash/Zsh can support recursive globbing such as:

```bash
**/*.log
```

depending on shell options.

---

# 16. systemd, Services & Logs

| # | Command | Description |
|---|---|---|
| 217 | `systemctl` | Start/stop/status/enable services. 🌍🔐 |
| 218 | `journalctl` | Read systemd journal logs. 🌍 |
| 219 | `systemd-analyze` | Inspect boot performance and systemd state. 🌍 |
| 220 | `dmesg` | Read kernel ring-buffer messages. 🔐 (access may be restricted) |
| 221 | `logger` | Send a message to the system log. |
| 222 | `logrotate` | Rotate/compress logs. 🌍 |
| 223 | `cron` | Schedule recurring jobs. 🌍 |
| 224 | `crontab` | View/edit user cron jobs. 🟡🌍 |
| 225 | `hostnamectl` | Query/set hostname in systemd-based systems. 🌍 |
| 226 | `timedatectl` | Query/set date/time and timezone in systemd-based systems. 🌍 |
| 227 | `loginctl` | Inspect/manage logins, sessions, and seats. 🌍 |
| 228 | `at` | Schedule a one-time job for later. 🌍 |
| 229 | `batch` | Run commands when system load permits. 🌍 |

Examples:

```bash
systemctl status nginx
systemctl restart nginx
journalctl -u nginx
journalctl -u nginx -f
journalctl -b
dmesg | tail
crontab -l
systemctl list-timers --all
hostnamectl

at now + 5 minutes -f backup.sh
atq        # list pending at jobs
atrm 3     # remove job number 3
```

⚠️ `at` and `batch` need the `atd` service to be running (check with `systemctl status atd`). `atrm` deletes a scheduled job without confirmation.

⚠️ `crontab -r` removes all scheduled jobs for the current user immediately. Prefer `crontab -ri` if you want an interactive confirmation prompt.

Common log locations vary by distro and configuration:

```text
/var/log/
/var/log/syslog
/var/log/messages
/var/log/auth.log
/var/log/secure
/var/log/kern.log
```

Do not assume every file exists on every Linux distribution; systemd journal may be the primary log source.

💡 `systemd` timers are typically a `.timer` unit plus a matching `.service` unit in `/etc/systemd/system/` (or packaged under `/usr/lib/systemd/system/`). Enable one with `systemctl enable --now <name>.timer`.

---

# 17. Package Managers

| Distribution family | Package manager | Common examples |
|---|---|---|
| Debian / Ubuntu | `apt` | `apt update`, `apt install package` |
| Fedora / RHEL | `dnf` | `dnf install package` |
| Arch | `pacman` | `pacman -S package` |
| Alpine | `apk` | `apk add package` |
| openSUSE | `zypper` | `zypper install package` |

| # | Command | Description |
|---|---|---|
| 230 | `apt` | Debian/Ubuntu package management. 🌍🔐 |
| 231 | `dnf` | Fedora/RHEL package management. 🌍🔐 |
| 232 | `pacman` | Arch package management. 🌍🔐 |
| 233 | `apk` | Alpine package management. 🌍🔐 |
| 234 | `zypper` | openSUSE package management. 🌍🔐 |

Always check the package manager appropriate to the distribution rather than assuming `apt` exists.

---

# 18. Hardware & Kernel Inspection

| # | Command | Description |
|---|---|---|
| 235 | `uname` | Kernel/system information. |
| 236 | `hostname` | Show/set hostname. 🔐 when changing |
| 237 | `date` | Display/set date/time. 🔐 when changing |
| 238 | `cal` | Display a calendar. |
| 239 | `lscpu` | CPU architecture/details. |
| 240 | `lsmem` | Memory layout/availability. |
| 241 | `lspci` | PCI hardware devices. |
| 242 | `lsusb` | USB devices. |
| 243 | `dmidecode` | DMI/SMBIOS hardware information. 🔐 |
| 244 | `inxi` | Broad system information. 🌍 |
| 245 | `lsmod` | Loaded kernel modules. |
| 246 | `modprobe` | Load/remove kernel modules. 🔐 |
| 247 | `rmmod` | Remove a kernel module. 🔐 |
| 248 | `xrandr` | Query/configure display outputs and resolutions (X11 only; Wayland uses compositor-specific tools). 🌍 |

💡 To inspect OS identity and version metadata:

```bash
cat /etc/os-release
```

---

# 19. Executables, Libraries & Binary Inspection

| # | Command | Description |
|---|---|---|
| 249 | `ldd` | Show shared-library dependencies. |
| 250 | `ldconfig` | Manage the shared-library cache. 🔐 |
| 251 | `readelf` | Inspect ELF executable/object metadata. |
| 252 | `objdump` | Inspect/disassemble object files and binaries. |
| 253 | `strings` | Extract human-readable strings from binary data. |
| 254 | `xxd` | Hex dump/create binary data. |
| 255 | `hexdump` | Display binary data in hexadecimal/other formats. |
| 256 | `od` | Octal/hex/decimal dump. |
| 257 | `nm` | List symbols from object files and binaries. |

These are particularly useful for debugging missing libraries, architecture mismatches, ELF issues, and unfamiliar binaries.

⚠️ `ldd` can execute the binary it inspects. For untrusted files, prefer safer static checks such as:

```bash
readelf -d ./binary | grep NEEDED
objdump -p ./binary | grep NEEDED
```

---

# 20. Checksums & Integrity

| # | Command | Description |
|---|---|---|
| 258 | `sha256sum` | SHA-256 checksum. |
| 259 | `sha512sum` | SHA-512 checksum. |
| 260 | `md5sum` | MD5 checksum; unsuitable for security-sensitive integrity/authentication. |
| 261 | `cksum` | CRC checksum and byte count. |
| 262 | `sum` | Legacy checksum utility. |
| 263 | `gpg` | Sign, verify, encrypt, and manage keys. |

Example:

```bash
sha256sum downloaded.iso
```

Compare the result with a trusted published checksum.

---

# 21. Version Control & Development Utilities

| # | Command | Description |
|---|---|---|
| 264 | `git` | Distributed version control. |
| 265 | `make` | Build automation. 🌍 |
| 266 | `shellcheck` | Static analysis for shell scripts. 🌍 |
| 267 | `shfmt` | Format shell scripts. 🌍 |
| 268 | `gdb` | GNU debugger for compiled programs. 🌍 |
| 269 | `valgrind` | Detect memory errors and leaks. 🌍 |

---

# 22. Terminal Multiplexing & Modern Replacements

| # | Command | Description |
|---|---|---|
| 270 | `tmux` | Persistent terminal sessions/panes. 🌍 |
| 271 | `screen` | Terminal multiplexer. |
| 272 | `entr` | Re-run commands when files change. 🌍 |
| 273 | `rg` / `ripgrep` | Faster recursive text search; respects `.gitignore` by default. 🌍 |
| 274 | `fd` | User-friendly alternative to many `find` workflows. 🌍 |
| 275 | `fzf` | Interactive fuzzy finder. 🌍 |
| 276 | `bat` | `cat` alternative with highlighting. 🌍 |
| 277 | `zoxide` | Smarter directory jumping. 🌍 |
| 278 | `eza` | Modern `ls` alternative. 🌍 |
| 279 | `tldr` | Concise command examples. 🌍 |

Note: `exa` is largely superseded by `eza`; use `eza` for a current recommendation.

---

# 23. Practical Troubleshooting Workflow

When something fails, work from simple evidence toward deeper diagnostics.

### 1. Check the exit status

```bash
command
echo $?
```

### 2. Read the first useful error

Do not immediately focus on the final wall of secondary errors.

### 3. Check logs

```bash
journalctl -u service-name
journalctl -xe
tail -f /var/log/some-log
```

### 4. Check resources

```bash
uptime
free -h
df -h
du -sh ./*
```

### 5. Check processes

```bash
ps aux
pgrep process-name
lsof -i :8080
```

### 6. Check networking

```bash
ip addr
ip route
ss -tuln
dig example.com
curl -I https://example.com
```

### 7. Inspect the service

```bash
systemctl status service-name
journalctl -u service-name -b
```

### 8. Go deeper only when necessary

```bash
strace command
perf trace command
```

Remember that tracing/profiling can add overhead.

---

# 24. Practical Recipes

## Backup a directory

```bash
tar -czf project-backup-$(date +%F).tar.gz ./project
```

## Synchronize directories/files

```bash
# Preview first (changes nothing)
rsync -avn --delete ./project/ backup-host:/srv/project/

# Then run for real
rsync -av --delete ./project/ backup-host:/srv/project/
```

💡 `rsync` is ideal for backups, mirroring, and efficient updates; use `-n` / `--dry-run` to preview.

⚠️ `--delete` removes files from the destination that do not exist in the source. A trailing slash on the source (`./project/`) copies the directory's contents; without it, the directory itself is copied.

## Find large files

```bash
find . -type f -size +100M -print
```

Or inspect disk usage interactively:

```bash
ncdu
```

## Find recently modified files

```bash
find . -type f -mtime -1
```

## Replace text across many files

First inspect matches:

```bash
grep -RIl -- "old-text" .
```

Then modify deliberately:

```bash
grep -RIlZ -- "old-text" . | xargs -0 -r sed -i 's/old-text/new-text/g'
```

`-Z` / `-0` handle spaces and newlines in filenames, and `-r` prevents `xargs` from running `sed` when there are no matches.

⚠️ Test the command on a small set or use version control / backups first.

## Monitor a log

```bash
tail -f /var/log/app.log
```

Or:

```bash
journalctl -u nginx -f
```

## Inspect a failed service

```bash
systemctl status nginx
journalctl -u nginx -b --no-pager
```

## Find which process owns a port

```bash
ss -ltnp 'sport = :8080'
```

Or:

```bash
lsof -i :8080
```

## Gracefully stop a process

```bash
kill PID
```

Wait a few seconds and check status before escalating:

```bash
ps -p PID
kill -KILL PID
```

`kill` sends `SIGTERM` by default; `kill -KILL` is a forced stop.

## Safely inspect an archive before extraction

```bash
tar -tf archive.tar.gz
unzip -l archive.zip
```

---

# 25. Security & Safety Rules

### `sudo`

Use the least privilege necessary. Prefer:

```bash
sudo command
```

over starting a long-lived root shell when you only need one privileged operation.

### `rm`

Never casually combine recursive/force options:

```bash
rm -rf
```

Before using a destructive glob, inspect it:

```bash
printf '%s\n' ./*.tmp
```

### `cp`, `mv`, and shell redirection

`cp`, `mv`, `>`, and `tee` can overwrite files silently unless you guard against it.

Examples:

```bash
cp -n src.txt dst.txt
mv -n src.txt dst.txt
cp -i src.txt dst.txt
mv -i src.txt dst.txt
set -o noclobber
```

Use `cp -i`, `mv -i`, `cp -n`, or `mv -n` when you want stricter overwrite protection.

### `chmod -R` / `chown -R`

Recursive permission and ownership changes are easy to misuse.

```bash
chmod -R 755 some-dir
chown -R user:group some-dir
```

Prefer a scoped target and verify before running.

### `dd`

Always double-check `if=` and especially `of=`:

```bash
dd if=input.img of=output.img
```

A reversed or mistyped destination can destroy a disk.

### SSH keys

Private keys should normally be accessible only by their owner:

```bash
chmod 600 ~/.ssh/id_ed25519
chmod 700 ~/.ssh
```

Never publish or paste private keys.

### Command injection

Do not build shell commands by blindly concatenating untrusted input.

Dangerous pattern:

```bash
sh -c "some_command $user_input"
```

Prefer passing arguments directly and quoting them:

```bash
some_command -- "$user_input"
```

When scripting, understand the difference between shell parsing, quoting, globbing, command substitution, and argument boundaries.

---

# 26. Aliases & Functions

Add personal aliases/functions to `~/.bashrc` or `~/.zshrc` as appropriate.

```bash
alias ll='ls -la'
alias gs='git status'

extract() {
    case "$1" in
        *.tar.gz|*.tgz) tar -xzf "$1" ;;
        *.tar.bz2)      tar -xjf "$1" ;;
        *.tar.xz)       tar -xJf "$1" ;;
        *.tar.zst|*.tzst) tar --zstd -xf "$1" ;;
        *.zip)           unzip "$1" ;;
        *)               printf 'Unknown archive: %s\n' "$1" ;;
    esac
}
```

💡 Avoid relying on aliases for safety-critical behavior: aliases can disappear in scripts, under `sudo`, or on other machines.

---

# 27. Make It Yours

Useful customizations:

- Customize `PS1` to show `user@host:directory (git-branch)$`.
- Use `tldr` for quick examples and `man` for authoritative details.
- Use `rg`, `fd`, `fzf`, `bat`, `eza`, and `zoxide` if they fit your workflow.
- Learn your shell's history and completion features.
- Keep destructive commands visibly distinct in your mental workflow.
- Put reusable functions in your shell configuration, but keep automation in scripts.

---

# 28. Terminal Fun & Eye Candy

| # | Tool | Description |
|---|---|---|
| 280 | `cmatrix` | Classic falling “Matrix” characters. 🌍 |
| 281 | `neofetch` | Display system info with ASCII distro art. 🌍 |
| 282 | `fastfetch` | Faster, modern alternative to `neofetch`. 🌍 |
| 283 | `cowsay` | Makes an ASCII cow say something. 🌍 |
| 284 | `cowthink` | Makes the cow think something. 🌍 |
| 285 | `fortune` | Prints a random quote/message. 🌍 |
| 286 | `lolcat` | Rainbow-colored terminal output. 🌍 |
| 287 | `figlet` | Turns text into large ASCII banners. 🌍 |
| 288 | `toilet` | Another ASCII-art text generator with effects. 🌍 |
| 289 | `sl` | A joke command for mistyping `ls`. 🌍 |
| 290 | `pv` | Shows progress while data flows through a pipe. 🌍 |
| 291 | `ranger` | Keyboard-driven terminal file manager. 🌍 |
| 292 | `nnn` | Very fast terminal file manager. 🌍 |
| 293 | `yazi` | Modern terminal file manager. 🌍 |
| 294 | `cava` | Terminal audio spectrum visualizer. 🌍 |
| 295 | `pipes.sh` | Animated pipes flowing around the terminal. 🌍 |
| 296 | `hollywood` | Simulates a ridiculous “hacker movie” terminal. 🌍 |
| 297 | `genact` | Fake activity generator that makes your terminal look busy. 🌍 |
| 298 | `nyancat` | Animated Nyan Cat in the terminal. 🌍 |
| 299 | `aafire` | ASCII fire effect. 🌍 |
| 300 | `oneko` | A little cat follows your cursor around. 🌍 |

These are fun tools and can be useful for demos, screen sharing, or just making a terminal feel less intimidating.

---

# 29. Quick Safety Summary

| Command/tool | Typical risk |
|---|---|
| `ls`, `pwd`, `file`, `stat`, `find` | 🟢 Usually safe |
| `find -delete`, `find -exec rm` | 🟡/🔴 Can delete files if the target is not explicitly checked |
| `cp`, `mv`, `>`, `tee` | 🟡 Can overwrite files unless guarded |
| `grep`, `less`, `head`, `tail`, `jq` | 🟢 Usually safe |
| `chmod`, `chown`, `chmod -R`, `chown -R` | 🟡 Changes system state |
| `mount`, `systemctl` | 🟡 Changes system state |
| `sudo` | 🟡/🔐 Privilege escalation |
| `kill`, `pkill`, `pkill -9` | 🟡/🔴 Process disruption |
| `rm -rf` | 🔴 Destructive |
| `dd` | 🔴 Potentially catastrophic |
| `mkfs` | 🔴 Destroys existing filesystem data |
| `fdisk` / partitioning | 🔴 Can destroy partitions/data |
| `fsck` | 🟡/🔴 Repair operations can be destructive |
| `userdel -r` | 🔴 Removes account/home data |
| `truncate`, `shred` | 🔴 Discards or overwrites file contents; `shred` is unreliable on SSDs and copy-on-write filesystems |
| `rsync --delete` | 🟡/🔴 Deletes destination files missing from the source; preview with `-n` first |
| `ufw`, `nft`, `iptables`, `firewall-cmd` | 🟡 Can block your own SSH session on remote machines |
| `crontab -r` | 🔴 Removes all of a user's scheduled jobs immediately |
| `lvremove`, `vgremove`, `pvremove` | 🔴 Destroys LVM volumes, groups, or metadata |
| `usermod -G` (without `-a`) | 🟡 Replaces the user's supplementary groups |
| `ldd` | 🟡 Can execute an inspected binary |
| `apt` / `dnf` / `pacman` / `apk` / `zypper` | 🌍 Distro-specific |

---

# 30. Final Rule

**If you don't know what a command does, don't guess.**

Start with:

```bash
command --help
man command
```

Then inspect the target, understand the arguments, and only execute destructive operations after verifying exactly what they will affect.
