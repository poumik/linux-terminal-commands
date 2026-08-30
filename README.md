Here’s my curated list of 200 most useful Linux terminal commands**—grouped by category for clarity, but numbered continuously. These are the heavy hitters I use daily as a sysadmin/developer.

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

### Advanced Disk, Filesystem & Block Operations

| # | Command | Description |
|---|---------|-------------|
| 101 | `dd` | Low‑level copy/conversion (e.g., `dd if=/dev/sda of=backup.img bs=4M`). |
| 102 | `sync` | Flush filesystem buffers to disk (force writes). |
| 103 | `mount` | Attach a filesystem to the directory tree (`-t` for type). |
| 104 | `umount` | Detach a mounted filesystem. |
| 105 | `fdisk` | Partition table manipulator (interactive, MBR/GPT). |
| 106 | `mkfs` | Build a filesystem on a partition (e.g., `mkfs.ext4 /dev/sdb1`). |
| 107 | `lsblk` | List block devices in a tree format (with sizes and mount points). |
| 108 | `blkid` | Locate/print block device attributes (UUID, filesystem type). |
| 109 | `e2fsck` | Check/repair an ext2/ext3/ext4 filesystem (run on unmounted). |
| 110 | `tune2fs` | Adjust tunable ext2/3/4 filesystem parameters (e.g., reserved blocks). |

---

### Niche Text & Data Transformation

| # | Command | Description |
|---|---------|-------------|
| 111 | `tac` | Reverse `cat` – print file lines in reverse order. |
| 112 | `rev` | Reverse each character in every line. |
| 113 | `paste` | Merge lines of multiple files side‑by‑side (column‑wise). |
| 114 | `join` | Join lines of two sorted files on a common field (like SQL join). |
| 115 | `comm` | Compare two sorted files line‑by‑line (shows unique/common). |
| 116 | `nl` | Number lines of a file (like `cat -n` but with more formatting). |
| 117 | `fold` | Wrap input lines to fit a specified width (e.g., `fold -w 80`). |
| 118 | `expand` | Convert tabs to spaces. |
| 119 | `unexpand` | Convert spaces to tabs (opposite of `expand`). |
| 120 | `seq` | Generate a sequence of numbers (`seq 1 10`). |

---

### Process Performance & Low‑Level Inspection

| # | Command | Description |
|---|---------|-------------|
| 121 | `lsof` | List **open files** (sockets, pipes, logs) – great for `lsof -i :80`. |
| 122 | `fuser` | Identify processes using a file/socket (`fuser -v /var/log/syslog`). |
| 123 | `iotop` | Real‑time disk I/O usage per process (requires root). |
| 124 | `iostat` | Report CPU and disk I/O statistics (from `sysstat` package). |
| 125 | `vmstat` | Virtual memory stats – processes, memory, paging, CPU. |
| 126 | `sar` | Collect, report, and save system activity data (powerful historical tool). |
| 127 | `pidof` | Find the PID of a running process by name (`pidof nginx`). |
| 128 | `nice` | Run a process with a modified scheduling priority (lower niceness = higher). |
| 129 | `renice` | Change the priority of an already‑running process. |
| 130 | `strace` | Trace system calls and signals – debug like a pro. |

---

### Hardware & Kernel Deep Dive

| # | Command | Description |
|---|---------|-------------|
| 131 | `lscpu` | Display CPU architecture info (cores, threads, model). |
| 132 | `lsmem` | List memory regions and their availability (NUMA aware). |
| 133 | `lspci` | Show all PCI devices (graphics, NICs, storage). |
| 134 | `lsusb` | List USB devices (tree view with `-t`). |
| 135 | `dmidecode` | Dump DMI/SMBIOS data – hardware serials, BIOS versions. |
| 136 | `inxi` | All‑in‑one system info script (great for support forums). |
| 137 | `neofetch` | Display system info in a pretty, distribution‑logo format. |
| 138 | `lsmod` | Show currently loaded kernel modules. |
| 139 | `modprobe` | Add or remove kernel modules (with dependency handling). |
| 140 | `rmmod` | Remove a kernel module (force with `-f`). |

---

### Advanced Networking (DNS, scanning, routing)

| # | Command | Description |
|---|---------|-------------|
| 141 | `dig` | DNS lookup utility – get A, MX, NS records with full details. |
| 142 | `nslookup` | Query DNS servers interactively or for a single host. |
| 143 | `host` | Simple DNS lookup (good for quick IP ↔ name resolution). |
| 144 | `nmap` | Network discovery and port scanning (`nmap -sP 192.168.1.0/24`). |
| 145 | `telnet` | Connect to remote hosts over TCP (used to test raw ports). |
| 146 | `mtr` | My TraceRoute – combines `ping` and `traceroute` in real‑time. |
| 147 | `iftop` | Real‑time network bandwidth usage per connection (like `top` for net). |
| 148 | `nethogs` | Show bandwidth usage per process (not just per interface). |
| 149 | `arp` | View/manage the ARP table (IP ↔ MAC address mapping). |
| 150 | `route` | Show or modify the IP routing table (deprecated, use `ip route`). |

---

### User & Group Administration

| # | Command | Description |
|---|---------|-------------|
| 151 | `useradd` | Create a new user account (`-m` for home dir). |
| 152 | `usermod` | Modify an existing user (groups, home, shell). |
| 153 | `userdel` | Delete a user account (`-r` removes home/mail). |
| 154 | `groupadd` | Create a new group. |
| 155 | `groupdel` | Delete a group. |
| 156 | `passwd` | Change a user’s password (root can change any). |
| 157 | `chage` | Manage password aging and expiry dates. |
| 158 | `groups` | Show which groups a user belongs to. |
| 159 | `whoami` | Print the effective current username. |
| 160 | `newgrp` | Log in to a new group (temporarily change primary group). |

---

### Job Scheduling & Shell Environment Control

| # | Command | Description |
|---|---------|-------------|
| 161 | `crontab` | Manage cron jobs for scheduled tasks (`-e` to edit). |
| 162 | `at` | Schedule a one‑time job to run at a specified time. |
| 163 | `batch` | Run jobs when system load averages are low. |
| 164 | `screen` | Terminal multiplexer (keep sessions alive; `tmux`’s elder sibling). |
| 165 | `env` | Run a command in a modified environment or show current env vars. |
| 166 | `printenv` | Print all or specific environment variables. |
| 167 | `set` | Show all shell variables and functions (or set shell options). |
| 168 | `unset` | Remove a shell variable or function. |
| 169 | `.` (source) | Execute a script in the **current** shell context (e.g., `source ~/.bashrc`). |
| 170 | `exec` | Replace the current shell with a command (no subshell). |

---

### Access Control Lists (ACLs) & Extended Attributes

| # | Command | Description |
|---|---------|-------------|
| 171 | `setfacl` | Set Access Control Lists (fine‑grained per‑user/group permissions). |
| 172 | `getfacl` | View ACLs on a file/directory. |
| 173 | `chattr` | Change **extended attributes** (e.g., `+i` to make immutable). |
| 174 | `lsattr` | List extended attributes of files. |
| 175 | `stat` | Display detailed file stats (size, inode, times, permissions). |
| 176 | `install` | Copy files and set attributes (used in Makefiles, like `cp` with chmod). |
| 177 | `mktemp` | Create a temporary file/directory safely (returns its path). |
| 178 | `realpath` | Resolve a canonical absolute path (resolves symlinks, `..`). |
| 179 | `split` | Split a large file into smaller pieces (by size or lines). |
| 180 | `csplit` | Split a file based on context/patterns (not just line count). |

---

### Checksums, Encoding & Binary Dumps

| # | Command | Description |
|---|---------|-------------|
| 181 | `base64` | Encode/decode data in base64 (great for embedding). |
| 182 | `md5sum` | Compute and verify MD5 checksums (fast, but cryptographically broken). |
| 183 | `sha256sum` | SHA‑256 hash – secure and widely used for integrity checks. |
| 184 | `sha512sum` | SHA‑512 hash – even stronger. |
| 185 | `cksum` | Print CRC checksum and byte count (POSIX standard). |
| 186 | `sum` | Older checksum (BSD or System V – not recommended). |
| 187 | `xxd` | Create hex dump of a file or reverse (convert hex back to binary). |
| 188 | `od` | Octal/hex dump of a file (octal by default). |
| 189 | `hexdump` | Display file contents in hex, decimal, ASCII (flexible output). |
| 190 | `strings` | Extract human‑readable text strings from binary files. |

---

### Shell Builtins & Scripting Power‑tools

| # | Command | Description |
|---|---------|-------------|
| 191 | `read` | Read a line from stdin into variables (interactive scripts). |
| 192 | `shift` | Shift positional parameters to the left (for parsing args). |
| 193 | `getopts` | Parse command‑line options in a standard way (built‑in). |
| 194 | `trap` | Catch signals and run commands on exit/interrupt (cleanup). |
| 195 | `bind` | Display or modify readline key bindings. |
| 196 | `fc` | List/edit/re‑run previous commands (fix mistakes). |
| 197 | `ulimit` | Set or display resource limits (open files, stack size, CPU time). |
| 198 | `wait` | Wait for a background process to finish (used in scripts). |
| 199 | `exit` | Terminate the current shell with an exit code. |
| 200 | `logout` | Log out of a login shell (close session). |

---

### Pro Tips
- **Combine them:** The real power comes from piping (`|`) – e.g., `ps aux | grep nginx`.
- **Read the manual:** `man command` is your best friend.
- **Practice:** Try `curl ifconfig.me` to get your public IP, or `find . -name "*.log" -exec tail -n 5 {} \;` to peek at all log files.
