Here’s my curated list of **100 most useful Linux terminal commands**—grouped by category for clarity, but numbered continuously. These are the heavy hitters I use daily as a sysadmin/developer.

---

### File & Directory Management (Navigation, CRUD, Links)

| # | Command | Description |
|---|---------|-------------|
| 1 | `ls` | List directory contents (`-la` for all details). |
| 2 | `cd` | Change directory (`cd ~` goes home). |
| 3 | `pwd` | Print current working directory. |
| 4 | `mkdir` | Create a new directory (`-p` for parent paths). |
| 5 | `rmdir` | Remove an **empty** directory. |
| 6 | `rm` | Remove files or directories (`-rf` with extreme caution). |
| 7 | `cp` | Copy files/directories (`-r` for recursive). |
| 8 | `mv` | Move or rename files/directories. |
| 9 | `touch` | Create an empty file or update its timestamp. |
| 10 | `ln` | Create links (`-s` for symbolic/soft links). |
| 11 | `find` | Search for files/directories by name, type, size, or time. |
| 12 | `locate` | Instant file search using a pre-built database (`updatedb` to refresh). |
| 13 | `which` | Show the full path of an executable. |
| 14 | `whereis` | Locate binary, source, and manual pages for a command. |
| 15 | `tree` | Display directory structure in a tree-like format. |

---

### Viewing Files (Pagers & Editors)

| # | Command | Description |
|---|---------|-------------|
| 16 | `cat` | Concatenate and print file content to stdout. |
| 17 | `less` | Scrollable file viewer (supports search, `/pattern`). |
| 18 | `more` | Older pager; `less` is usually better. |
| 19 | `head` | Show first N lines of a file (default 10). |
| 20 | `tail` | Show last N lines (use `-f` to follow live logs). |
| 21 | `nano` | Simple, beginner-friendly terminal text editor. |
| 22 | `vim` | Powerful modal text editor (install `vim` if not present). |

---

### Text Processing (Search, Filter, Transform)

| # | Command | Description |
|---|---------|-------------|
| 23 | `grep` | Search for patterns in text (regex). `-i` ignore case, `-r` recursive. |
| 24 | `sed` | Stream editor – find/replace, delete lines, etc. |
| 25 | `awk` | Pattern-scanning & text-processing language (great for columns). |
| 26 | `cut` | Extract specific columns/fields from lines (`-d` delimiter, `-f` fields). |
| 27 | `sort` | Sort lines alphabetically/numerically. |
| 28 | `uniq` | Report or omit repeated lines (usually used after `sort`). |
| 29 | `wc` | Count lines, words, and characters (`-l` for just lines). |
| 30 | `tr` | Translate or delete characters (e.g., lower→upper). |
| 31 | `diff` | Show line-by-line differences between two files. |
| 32 | `patch` | Apply a diff file to update source code/text. |
| 33 | `tee` | Read from stdin and write to both stdout and a file. |
| 34 | `xargs` | Build and execute commands from stdin (passes output as arguments). |

---

### Permissions & Ownership

| # | Command | Description |
|---|---------|-------------|
| 35 | `chmod` | Change file permissions (e.g., `chmod +x script.sh`). |
| 36 | `chown` | Change file owner and group. |
| 37 | `chgrp` | Change group ownership only. |
| 38 | `umask` | Set default permission mask for new files/dirs. |
| 39 | `sudo` | Execute a command as another user (usually root). |
| 40 | `su` | Switch user (or become root with `su -`). |

---

### Process & System Monitoring

| # | Command | Description |
|---|---------|-------------|
| 41 | `ps` | Snapshot of current processes (`aux` for all users). |
| 42 | `top` | Real‑time process viewer (CPU/memory). |
| 43 | `htop` | Improved interactive process monitor (install separately). |
| 44 | `kill` | Send signals to a process by PID (`-9` to force kill). |
| 45 | `killall` | Kill all processes by name. |
| 46 | `jobs` | List active background jobs in the current shell. |
| 47 | `bg` | Resume a suspended job in the background. |
| 48 | `fg` | Bring a background job to the foreground. |
| 49 | `nohup` | Run a command immune to hangups (keeps running after logout). |
| 50 | `uptime` | Show how long the system has been running + load average. |
| 51 | `free` | Display memory usage (`-h` for human‑readable). |
| 52 | `df` | Show disk space usage of all mounted filesystems (`-h`). |
| 53 | `du` | Estimate file/directory space usage (`-sh` for summary). |
| 54 | `dmesg` | Print kernel ring buffer (boot messages & hardware logs). |
| 55 | `uname` | System info (`-a` for all details). |
| 56 | `hostname` | Show or set the system’s hostname. |
| 57 | `date` | Display or set the system date/time. |
| 58 | `cal` | Show a calendar in the terminal. |
| 59 | `who` | Show who is currently logged in. |
| 60 | `w` | Show who is logged in and what they are doing. |
| 61 | `last` | Show login history (reads `/var/log/wtmp`). |
| 62 | `id` | Print user and group IDs for the current user. |

---

### Networking

| # | Command | Description |
|---|---------|-------------|
| 63 | `ping` | Test network connectivity to a host (ICMP). |
| 64 | `traceroute` | Trace the route packets take to a destination. |
| 65 | `ss` | Socket statistics – modern replacement for `netstat` (e.g., `ss -tuln`). |
| 66 | `ip` | Show/manage network interfaces, routes, and tunnels (`ip a`). |
| 67 | `ifconfig` | Older interface config tool (still common, but `ip` is preferred). |
| 68 | `curl` | Transfer data from/to a server (supports HTTP, FTP, etc.). |
| 69 | `wget` | Non‑interactive network downloader (great for recursive mirrors). |
| 70 | `scp` | Securely copy files over SSH. |
| 71 | `rsync` | Fast, incremental file sync over SSH or locally. |
| 72 | `ssh` | Secure Shell – remote login and command execution. |
| 73 | `nc` (netcat) | Networking Swiss‑army knife – read/write TCP/UDP, port scanning. |

---

### Archiving & Compression

| # | Command | Description |
|---|---------|-------------|
| 74 | `tar` | Tape archiver – create/extract `.tar` files (`-czvf` for gzip). |
| 75 | `gzip` | Compress/decompress files (GNU zip). |
| 76 | `zip` | Package and compress in Windows‑compatible `.zip` format. |
| 77 | `unzip` | Extract `.zip` archives. |
| 78 | `bzip2` | Higher‑compression block‑sorting compressor. |
| 79 | `xz` | Very high compression ratio (`.xz` format). |

---

### Package Management (distro‑specific)

| # | Command | Description |
|---|---------|-------------|
| 80 | `apt` | Debian/Ubuntu package manager (install, update, upgrade). |
| 81 | `dnf` | RHEL/Fedora next‑gen package manager (replaces `yum`). |
| 82 | `pacman` | Arch Linux package manager. |
| 83 | `shutdown` | Power off or reboot the system (`-h now`, `-r now`). |

---

### Shell Utilities & Shortcuts

| # | Command | Description |
|---|---------|-------------|
| 84 | `clear` | Clear the terminal screen. |
| 85 | `history` | Show command history (repeat with `!123`). |
| 86 | `alias` | Create command shortcuts (e.g., `alias ll='ls -la'`). |
| 87 | `export` | Set environment variables. |
| 88 | `echo` | Display a line of text or variable value. |
| 89 | `man` | Display the manual page for any command. |
| 90 | `whatis` | Show a one‑line summary of a command’s purpose. |
| 91 | `type` | Describe how a command would be interpreted (builtin, alias, binary). |
| 92 | `time` | Measure the execution time of a command. |
| 93 | `sleep` | Pause for a specified number of seconds. |
| 94 | `readlink` | Print the value of a symbolic link (or canonical path with `-f`). |
| 95 | `dirname` | Strip the last component from a file path (get the directory). |
| 96 | `basename` | Strip the directory path and get the filename. |
| 97 | `printf` | Format and print data (more powerful than `echo`). |
| 98 | `yes` | Repeatedly output a line (useful for piping to confirm prompts). |
| 99 | `watch` | Run a command repeatedly and show output every 2 seconds (e.g., `watch -n1 free`). |
| 100 | `tmux` | Terminal multiplexer – keep sessions alive, split panes, detach/reattach. |

---

### Pro Tips
- **Combine them:** The real power comes from piping (`|`) – e.g., `ps aux | grep nginx`.
- **Read the manual:** `man command` is your best friend.
- **Practice:** Try `curl ifconfig.me` to get your public IP, or `find . -name "*.log" -exec tail -n 5 {} \;` to peek at all log files.
