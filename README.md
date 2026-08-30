Here’s my curated list of 200 most useful Linux terminal commands**—grouped by category for clarity, but numbered continuously. These are the heavy hitters I use daily as a sysadmin/developer.

# The Linux Terminal Reference

---

##  File & Directory Management

| # | Command | Description |
|---|---------|-------------|
| 1 | `ls` | List directory contents (`-la` for all details). |
| 2 | `cd` | Change directory (`cd ~` goes home). |
| 3 | `pwd` | Print current working directory. |
| 4 | `mkdir` | Create a new directory (`-p` for parent paths). |
| 5 | `rmdir` | Remove an empty directory. |
| 6 | `rm` | Remove files or directories (`-rf` with extreme caution — see note below). |
| 7 | `cp` | Copy files/directories (`-r` for recursive). |
| 8 | `mv` | Move or rename files/directories. |
| 9 | `touch` | Create an empty file or update its timestamp. |
| 10 | `ln` | Create links (`-s` for symbolic/soft links). |
| 11 | `find` | Search for files/directories by name, type, size, or time. |
| 12 | `locate` | Instant file search using a pre-built database (`updatedb` to refresh). |
| 13 | `which` | Show the full path of an executable. |
| 14 | `whereis` | Locate binary, source, and manual pages for a command. |
| 15 | `tree` | Display directory structure in a tree-like format. |

##  Viewing Files (Pagers & Editors)

| # | Command | Description |
|---|---------|-------------|
| 16 | `cat` | Concatenate and print file content to stdout. |
| 17 | `less` | Scrollable file viewer (supports search, `/pattern`). |
| 18 | `more` | Older pager; `less` is usually better. |
| 19 | `head` | Show first N lines of a file (default 10). |
| 20 | `tail` | Show last N lines (`-f` to follow live logs). |
| 21 | `nano` | Simple, beginner-friendly terminal text editor. |
| 22 | `vim` | Powerful modal text editor. |

##  Text Processing

| # | Command | Description |
|---|---------|-------------|
| 23 | `grep` | Search for patterns in text (regex). `-i` ignore case, `-r` recursive. |
| 24 | `sed` | Stream editor – find/replace, delete lines, etc. |
| 25 | `awk` | Pattern-scanning & text-processing language (great for columns). |
| 26 | `cut` | Extract specific columns/fields from lines (`-d` delimiter, `-f` fields). |
| 27 | `sort` | Sort lines alphabetically/numerically. |
| 28 | `uniq` | Report or omit repeated lines (usually used after `sort`). |
| 29 | `wc` | Count lines, words, and characters (`-l` for just lines). |
| 30 | `tr` | Translate or delete characters. |
| 31 | `diff` | Show line-by-line differences between two files. |
| 32 | `patch` | Apply a diff file to update source code/text. |
| 33 | `tee` | Read from stdin and write to both stdout and a file. |
| 34 | `xargs` | Build and execute commands from stdin. `-P` runs them in parallel. |
| 35 | `column` | Pretty-print tabular text into aligned columns (`column -t`). |

##  Permissions & Ownership

| # | Command | Description |
|---|---------|-------------|
| 36 | `chmod` | Change file permissions (e.g., `chmod +x script.sh`). |
| 37 | `chown` | Change file owner and group. |
| 38 | `chgrp` | Change group ownership only. |
| 39 | `umask` | Set default permission mask for new files/dirs. |
| 40 | `sudo` | Execute a command as another user (usually root). |
| 41 | `su` | Switch user (or become root with `su -`). |

##  Process & System Monitoring

| # | Command | Description |
|---|---------|-------------|
| 42 | `ps` | Snapshot of current processes (`aux` for all users). |
| 43 | `top` | Real-time process viewer (CPU/memory). |
| 44 | `htop` | Improved interactive process monitor. |
| 45 | `btop` | Newer, prettier alternative to htop/top with graphs built in. |
| 46 | `kill` | Send signals to a process by PID (`-9` to force kill). |
| 47 | `killall` | Kill all processes by name. |
| 48 | `jobs` | List active background jobs in the current shell. |
| 49 | `bg` | Resume a suspended job in the background. |
| 50 | `fg` | Bring a background job to the foreground. |
| 51 | `nohup` | Run a command immune to hangups (keeps running after logout). |
| 52 | `timeout` | Run a command but kill it if it exceeds a time limit. |
| 53 | `uptime` | Show how long the system has been running + load average. |
| 54 | `free` | Display memory usage (`-h` for human-readable). |
| 55 | `df` | Show disk space usage of all mounted filesystems (`-h`). |
| 56 | `du` | Estimate file/directory space usage (`-sh` for summary). |
| 57 | `dmesg` | Print kernel ring buffer (boot messages & hardware logs). |
| 58 | `uname` | System info (`-a` for all details). |
| 59 | `hostname` | Show or set the system's hostname. |
| 60 | `date` | Display or set the system date/time. |
| 61 | `cal` | Show a calendar in the terminal. |
| 62 | `who` | Show who is currently logged in. |
| 63 | `w` | Show who is logged in and what they are doing. |
| 64 | `last` | Show login history (reads `/var/log/wtmp`). |
| 65 | `id` | Print user and group IDs for the current user. |

##  Networking

| # | Command | Description |
|---|---------|-------------|
| 66 | `ping` | Test network connectivity to a host (ICMP). |
| 67 | `traceroute` | Trace the route packets take to a destination. |
| 68 | `ss` | Socket statistics – modern replacement for `netstat` (e.g. `ss -tuln`). |
| 69 | `ip` | Show/manage network interfaces, routes, and tunnels (`ip a`). |
| 70 | `ifconfig` | Older interface config tool; `ip` is preferred now. |
| 71 | `curl` | Transfer data from/to a server (HTTP, FTP, etc.). |
| 72 | `wget` | Non-interactive network downloader (recursive mirrors). |
| 73 | `scp` | Securely copy files over SSH. |
| 74 | `rsync` | Fast, incremental file sync over SSH or locally. |
| 75 | `ssh` | Secure Shell – remote login and command execution. |
| 76 | `nc` (netcat) | Networking Swiss-army knife – read/write TCP/UDP, port scanning. |
| 77 | `openssl` | Certificates, hashing, quick encryption/decryption from the CLI. |

##  Archiving & Compression

| # | Command | Description |
|---|---------|-------------|
| 78 | `tar` | Create/extract `.tar` archives (`-czvf` for gzip). |
| 79 | `gzip` | Compress/decompress files (GNU zip). |
| 80 | `zip` | Package and compress in Windows-compatible `.zip` format. |
| 81 | `unzip` | Extract `.zip` archives. |
| 82 | `bzip2` | Higher-compression block-sorting compressor. |
| 83 | `xz` | Very high compression ratio (`.xz` format). |

##  Package Management (distro-specific)

| # | Command | Description |
|---|---------|-------------|
| 84 | `apt` | Debian/Ubuntu package manager. |
| 85 | `dnf` | RHEL/Fedora next-gen package manager (replaces `yum`). |
| 86 | `pacman` | Arch Linux package manager. |
| 87 | `shutdown` | Power off or reboot the system (`-h now`, `-r now`). |

##  Shell Utilities & Shortcuts

| # | Command | Description |
|---|---------|-------------|
| 88 | `clear` | Clear the terminal screen. |
| 89 | `history` | Show command history (repeat with `!123`). |
| 90 | `alias` | Create command shortcuts (e.g. `alias ll='ls -la'`). |
| 91 | `export` | Set environment variables. |
| 92 | `echo` | Display a line of text or variable value. |
| 93 | `man` | Display the manual page for any command. |
| 94 | `whatis` | Show a one-line summary of a command's purpose. |
| 95 | `type` | Describe how a command would be interpreted. |
| 96 | `time` | Measure the execution time of a command. |
| 97 | `sleep` | Pause for a specified number of seconds. |
| 98 | `readlink` | Print the value of a symbolic link (`-f` for canonical path). |
| 99 | `dirname` | Strip the last component from a file path. |
| 100 | `basename` | Strip the directory path and get the filename. |
| 101 | `printf` | Format and print data (more powerful than `echo`). |
| 102 | `yes` | Repeatedly output a line (pipe into confirm prompts). |
| 103 | `watch` | Run a command repeatedly, refreshing output (e.g. `watch -n1 free`). |
| 104 | `tmux` | Terminal multiplexer – keep sessions alive, split panes, detach/reattach. |
| 105 | `entr` | Rerun a command whenever watched files change — great for dev loops. |

##  Advanced Disk, Filesystem & Block Operations

| # | Command | Description |
|---|---------|-------------|
| 106 | `dd` | Low-level copy/conversion (e.g. `dd if=/dev/sda of=backup.img bs=4M`). |
| 107 | `sync` | Flush filesystem buffers to disk. |
| 108 | `mount` | Attach a filesystem to the directory tree. |
| 109 | `umount` | Detach a mounted filesystem. |
| 110 | `fdisk` | Partition table manipulator (interactive, MBR/GPT). |
| 111 | `mkfs` | Build a filesystem on a partition. |
| 112 | `lsblk` | List block devices in a tree format. |
| 113 | `blkid` | Locate/print block device attributes (UUID, filesystem type). |
| 114 | `e2fsck` | Check/repair an ext2/3/4 filesystem. |
| 115 | `tune2fs` | Adjust tunable ext2/3/4 filesystem parameters. |

##  Niche Text & Data Transformation

| # | Command | Description |
|---|---------|-------------|
| 116 | `tac` | Reverse `cat` – print file lines in reverse order. |
| 117 | `rev` | Reverse each character in every line. |
| 118 | `paste` | Merge lines of multiple files side-by-side. |
| 119 | `join` | Join lines of two sorted files on a common field. |
| 120 | `comm` | Compare two sorted files line-by-line. |
| 121 | `nl` | Number lines of a file. |
| 122 | `fold` | Wrap input lines to fit a specified width. |
| 123 | `expand` | Convert tabs to spaces. |
| 124 | `unexpand` | Convert spaces to tabs. |
| 125 | `seq` | Generate a sequence of numbers (`seq 1 10`). |
| 126 | `jq` | Parse, filter, and pretty-print JSON — essential if you touch APIs. |

##  Process Performance & Low-Level Inspection

| # | Command | Description |
|---|---------|-------------|
| 127 | `lsof` | List open files/sockets (great for `lsof -i :80`). |
| 128 | `fuser` | Identify processes using a file/socket. |
| 129 | `iotop` | Real-time disk I/O usage per process (needs root). |
| 130 | `iostat` | Report CPU and disk I/O statistics. |
| 131 | `vmstat` | Virtual memory stats – processes, memory, paging, CPU. |
| 132 | `sar` | Collect, report, and save historical system activity data. |
| 133 | `pidof` | Find the PID of a running process by name. |
| 134 | `nice` | Run a process with a modified scheduling priority. |
| 135 | `renice` | Change the priority of an already-running process. |
| 136 | `strace` | Trace system calls and signals. Adds real overhead — use for debugging, not in production paths. |
| 137 | `ltrace` | Like `strace` but traces library calls instead of syscalls. |
| 138 | `perf` | Modern Linux profiler; `perf trace` is a lighter-weight sibling to `strace`. |

##  Hardware & Kernel Deep Dive

| # | Command | Description |
|---|---------|-------------|
| 139 | `lscpu` | Display CPU architecture info. |
| 140 | `lsmem` | List memory regions and their availability. |
| 141 | `lspci` | Show all PCI devices. |
| 142 | `lsusb` | List USB devices (`-t` for tree view). |
| 143 | `dmidecode` | Dump DMI/SMBIOS data – hardware serials, BIOS versions. |
| 144 | `inxi` | All-in-one system info script. |
| 145 | `neofetch` | Display system info in a pretty, distro-logo format. |
| 146 | `lsmod` | Show currently loaded kernel modules. |
| 147 | `modprobe` | Add or remove kernel modules with dependency handling. |
| 148 | `rmmod` | Remove a kernel module (`-f` to force). |

##  Advanced Networking (DNS, scanning, routing)

| # | Command | Description |
|---|---------|-------------|
| 149 | `dig` | DNS lookup utility – A, MX, NS records. |
| 150 | `nslookup` | Query DNS servers interactively or for a single host. |
| 151 | `host` | Simple DNS lookup. |
| 152 | `nmap` | Network discovery and port scanning. |
| 153 | `telnet` | Connect to remote hosts over TCP (testing raw ports). |
| 154 | `mtr` | Combines `ping` and `traceroute` in real-time. |
| 155 | `iftop` | Real-time network bandwidth usage per connection. |
| 156 | `nethogs` | Show bandwidth usage per process. |
| 157 | `arp` | View/manage the ARP table. |
| 158 | `route` | Show/modify IP routing table (deprecated — use `ip route`). |

##  User & Group Administration

| # | Command | Description |
|---|---------|-------------|
| 159 | `useradd` | Create a new user account (`-m` for home dir). |
| 160 | `usermod` | Modify an existing user. |
| 161 | `userdel` | Delete a user account (`-r` removes home/mail). |
| 162 | `groupadd` | Create a new group. |
| 163 | `groupdel` | Delete a group. |
| 164 | `passwd` | Change a user's password. |
| 165 | `chage` | Manage password aging and expiry dates. |
| 166 | `groups` | Show which groups a user belongs to. |
| 167 | `whoami` | Print the effective current username. |
| 168 | `newgrp` | Log in to a new group temporarily. |

##  Job Scheduling & Shell Environment Control

| # | Command | Description |
|---|---------|-------------|
| 169 | `crontab` | Manage cron jobs (`-e` to edit). |
| 170 | `at` | Schedule a one-time job. |
| 171 | `batch` | Run jobs when system load is low. |
| 172 | `screen` | Terminal multiplexer, tmux's elder sibling. |
| 173 | `env` | Run a command in a modified environment, or show current env vars. |
| 174 | `printenv` | Print all or specific environment variables. |
| 175 | `set` | Show all shell variables/functions or set shell options. |
| 176 | `unset` | Remove a shell variable or function. |
| 177 | `.` (source) | Execute a script in the current shell context. |
| 178 | `exec` | Replace the current shell with a command. |

##  systemd — Service & Log Management

Missing from the original list entirely, and essential on most modern distros.

| # | Command | Description |
|---|---------|-------------|
| 179 | `systemctl` | Start, stop, enable, and check status of services (`systemctl status nginx`). |
| 180 | `journalctl` | Read the systemd journal/logs (`journalctl -xe`, `journalctl -u nginx -f`). |
| 181 | `systemd-analyze` | Break down and inspect boot time. |

##  Version Control

Not a "core Linux command" per se, but used more than most of this list by
practically everyone who works in a terminal.

| # | Command | Description |
|---|---------|-------------|
| 182 | `git` | Distributed version control — status, commit, branch, diff, log, etc. |

##  Access Control Lists (ACLs) & Extended Attributes

| # | Command | Description |
|---|---------|-------------|
| 183 | `setfacl` | Set fine-grained per-user/group permissions. |
| 184 | `getfacl` | View ACLs on a file/directory. |
| 185 | `chattr` | Change extended attributes (e.g. `+i` for immutable). |
| 186 | `lsattr` | List extended attributes of files. |
| 187 | `stat` | Display detailed file stats. |
| 188 | `install` | Copy files and set attributes (used in Makefiles). |
| 189 | `mktemp` | Create a temporary file/directory safely. |
| 190 | `realpath` | Resolve a canonical absolute path. |
| 191 | `split` | Split a large file into smaller pieces. |
| 192 | `csplit` | Split a file based on context/patterns. |

##  Checksums, Encoding & Binary Dumps

| # | Command | Description |
|---|---------|-------------|
| 193 | `base64` | Encode/decode data in base64. |
| 194 | `md5sum` | Compute MD5 checksums (fast, but cryptographically broken). |
| 195 | `sha256sum` | Secure, widely used integrity check hash. |
| 196 | `sha512sum` | Even stronger hash. |
| 197 | `cksum` | Print CRC checksum and byte count. |
| 198 | `sum` | Older checksum (not recommended). |
| 199 | `xxd` | Hex dump of a file (or reverse). |
| 200 | `od` | Octal/hex dump of a file. |
| 201 | `hexdump` | Display file contents in hex/decimal/ASCII. |
| 202 | `strings` | Extract human-readable text strings from binary files. |

##  Shell Builtins & Scripting Power-tools

| # | Command | Description |
|---|---------|-------------|
| 203 | `read` | Read a line from stdin into variables. |
| 204 | `shift` | Shift positional parameters to the left. |
| 205 | `getopts` | Parse command-line options in a standard way. |
| 206 | `trap` | Catch signals and run cleanup commands on exit/interrupt. |
| 207 | `bind` | Display or modify readline key bindings. |
| 208 | `fc` | List/edit/re-run previous commands. |
| 209 | `ulimit` | Set or display resource limits. |
| 210 | `wait` | Wait for a background process to finish. |
| 211 | `exit` | Terminate the current shell with an exit code. |
| 212 | `logout` | Log out of a login shell. |

##  Modern Replacements (not always preinstalled, worth adding)

These aren't core Unix tools, but each replaces something above with dramatically
better ergonomics. Most are one `apt install` / `brew install` away.

| Command | Replaces | Why |
|---------|----------|-----|
| `ripgrep` (`rg`) | `grep -r` | Much faster, respects `.gitignore` by default. |
| `fd` | `find` | Sane defaults, far less syntax to remember. |
| `fzf` | `Ctrl+R` history search | Interactive fuzzy finder — bind it to your history and file picking. |
| `bat` | `cat` | Syntax highlighting, line numbers, git-diff markers. |
| `zoxide` | `cd` | Learns your habits; `z proj` jumps to wherever you've `cd`'d before. |
| `ncdu` | `du -sh */` | Interactive disk-usage browser instead of a static list. |
| `exa` / `eza` | `ls` | Git-aware, icons, tree view built in. |
| `tldr` | `man` | Practical usage examples instead of the full manual. |

---

##  Pro Tips

###  Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl+A` | Jump to beginning of line. |
| `Ctrl+E` | Jump to end of line. |
| `Alt+B` / `Alt+F` | Move backward/forward one word. |
| `Ctrl+U` | Delete everything before the cursor. |
| `Ctrl+K` | Delete everything after the cursor. |
| `Ctrl+W` | Delete the word before the cursor. |
| `Ctrl+R` | Reverse search history (or bind `fzf` here for something much better). |
| `Ctrl+L` | Clear screen without leaving the home row. |
| `Ctrl+D` | Exit current shell/logout. |
| `Ctrl+Z` | Suspend current process (`fg` to bring it back). |
| `Ctrl+X Ctrl+E` | Open the current command line in `$EDITOR` — great for fixing a gnarly multi-line command instead of fighting a single-line buffer. |

###  Command History

- `!!` — Run the last command again (`sudo !!` when you forgot `sudo`). **Note:** this is bash's bang-syntax; it mostly works the same in zsh but word-splitting behaves slightly differently — test it in your actual shell before relying on it under pressure.
- `!$` — Expands to the last argument of the previous command (`mkdir new-folder && cd !$`).
- `!^` — Expands to the first argument of the previous command.
- `!string` — Execute the most recent command starting with "string".
- `Ctrl+R` — Use it until it's muscle memory, or replace it with `fzf` for a much better experience.

###  Brace Expansion & Globbing

- `{a,b,c}` — expands to multiple arguments: `mkdir -p project/{src,dist,tests,docs}`.
- `{1..10}` — number sequences: `touch file_{1..10}.txt`.
- `**` (bash 4+/zsh) — recursive globbing: `ls **/*.log`.
- `shopt -s extglob` then `rm !(*.jpg)` — delete everything except a pattern.

###  Pipes & Redirection

- `|&` — pipes both stdout and stderr: `command |& grep error`.
- `<(command)` — process substitution, treats output as a file: `diff <(ls dir1) <(ls dir2)`.
- `&> filename.txt` — shorthand for redirecting all output to a file.
- `tee` — write to a file while still watching it live: `./script.sh | tee output.log`.

###  Job Control

- `command &` — run in the background immediately.
- `Ctrl+Z` then `bg` — suspend a foreground job, push it to background.
- `jobs -l` — list background jobs with PIDs.
- `disown -h %1` — detach a background job so it survives closing the terminal.

###  Smarter Searching

- `grep -r --include="*.py" "function_name" .` — search only within Python files.
- `grep -C 5 error log.txt` — 5 lines of context before and after a match.
- `find . -type f -size +100M` — find files over 100MB.
- `find . -mtime -1` — files modified in the last 24 hours.
- `find . -name "*.conf" -exec sed -i 's/old/new/g' {} \;` — recursive find-and-replace.
- Or just use `rg` — it's faster and defaults to sane behavior.

###  Aliases & Functions

```bash
# Add to ~/.bashrc or ~/.zshrc
alias ll='ls -la --color=auto'
alias gs='git status'
alias myip='curl -s ifconfig.me'

# Extract any archive type
extract() {
  if [ -f "$1" ] ; then
    case "$1" in
      *.tar.bz2) tar xvjf "$1" ;;
      *.tar.gz)  tar xvzf "$1" ;;
      *.zip)     unzip "$1" ;;
      *) echo "I don't know how to extract '$1'" ;;
    esac
  fi
}
```

###  Safety Nets (revised)

- **Skip `alias rm='rm -i'`.** It trains you to reflexively hit `y`/Enter on delete prompts, which defeats its own purpose — and it silently disappears in scripts, `sudo`, or other machines where the alias isn't set, so you can't actually rely on it. Better: install `trash-cli` so deletes go to a recoverable trash instead of vanishing instantly, and get in the habit of running `ls` on a glob before you `rm -rf` it.
- `chmod -R u+rwX ./folder` — mass-fix permissions on a mixed file/folder structure (uppercase `X` only adds execute to things that already have it somewhere).
- `ls -ltr` — list files oldest-last, so the newest is at the bottom near your prompt.
- `Ctrl+_` — undo text editing in Bash, even after typing a long command.
- `set -euo pipefail` at the top of every bash script — turns silent failures (unset variables, a failed command mid-pipeline) into loud, immediate ones instead of a script that limps along and corrupts something.

###  Debugging Mindset

1. Check the exit code first: `echo $?` (0 = success).
2. Read the *first* error message, not the wall of red text — scroll to the top.
3. Check the logs before anything else: `journalctl -xe` (systemd) or `tail -f /var/log/syslog`.
4. Reach for `strace`/`ltrace`/`perf trace` when you need to see what a process is actually doing — but know they add real overhead, so use them to debug, not in anything performance- or production-sensitive.
5. `man` is the reference; `tldr` is faster for "just show me an example."

###  Make It Yours

- Customize `PS1` to show `user@host:~/project (git-branch)$`.
- Install `tldr` for practical examples instead of full manuals.
- Install `bat` for a `cat` with syntax highlighting.
- Install `exa`/`eza` for a git-aware, icon-friendly `ls`.

**The real force multiplier:** spend 10 minutes once on your `.bashrc`/`.zshrc` —
aliases, a couple of the modern replacements above, and `set -euo pipefail` in
your scripts — and it pays for itself hundreds of times over.
