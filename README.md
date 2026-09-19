# Linux Terminal Reference

A practical Linux command reference for sysadmins, developers, students, and advanced users.

**[Browse the full Linux terminal reference →](linux-terminal-commands.md)**

---

## About

This repository contains a comprehensive, easy-to-scan reference covering Linux commands, shell concepts, troubleshooting techniques, practical recipes, and safety guidelines.

It is designed for:

- Learning Linux fundamentals
- Quickly looking up unfamiliar commands
- Troubleshooting systems and services
- Writing safer shell scripts
- Reviewing networking, storage, permissions, and process-management tools

---

## License

This project is licensed under the [MIT License](LICENSE.txt).

---

## Disclaimer

This repository is for educational and reference purposes only.

- Commands and options can vary by Linux distribution, shell, version, and installed packages.
- Always verify what a command does before running it on a real system.
- Destructive commands such as `rm`, `mkfs`, `dd`, `fdisk`, and privileged system changes should be reviewed carefully and tested in safe environments when possible.
- This material is not a substitute for official distro documentation, man pages, or system-specific operational procedures.

---

## Contents

### Command fundamentals

- Command discovery and help
- Files and directory management
- Viewing and editing files
- Text processing and data transformation
- Pipelines and redirection

### System administration

- Permissions and ownership
- Users and groups
- Processes and job control
- System and performance monitoring
- Storage and filesystems
- `systemd`, services, and logs
- Package managers
- Hardware and kernel inspection

### Networking

- Network interfaces, routes, and sockets
- DNS diagnostics
- Connectivity testing
- HTTP and file transfers
- SSH and secure file transfer
- Network discovery and port scanning

### Shell scripting

- Environment variables and shell builtins
- Quoting and argument handling
- Exit codes and conditions
- Loops and functions
- Shell options such as `set -euo pipefail`
- History, shortcuts, aliases, and globbing

### Developer and diagnostic tools

- Archives and compression
- Executable and binary inspection
- Checksums and integrity verification
- Git and build utilities
- Terminal multiplexers
- Modern command-line replacements such as `rg`, `fd`, `fzf`, `bat`, and `eza`

### Practical guidance

- Troubleshooting workflows
- Backup and file-search recipes
- Log monitoring
- Service inspection
- Port ownership checks
- Security and command-safety guidance
- Terminal fun and eye-candy tools

---

## Safety legend

| Marker | Meaning |
|---|---|
| 🟢 | **Safe** — normally read-only or low-risk |
| 🟡 | **Caution** — changes state or configuration but is usually recoverable |
| 🔴 | **Destructive** — may delete, overwrite, repartition, or seriously damage data |
| 🔐 | **Privilege required** — commonly requires `sudo` or elevated permissions |
| 🌍 | **Not universal** — depends on the distro, shell, or installed packages |
| 💡 | **Tip** — useful shortcut or best practice |

---

## Safety first

Before running an unfamiliar command:

```bash
command --help
man command
```

Then inspect the target, understand the arguments, and avoid destructive operations until you know what they affect.

---

## Repository layout

- [`linux-terminal-commands.md`](linux-terminal-commands.md) — the full reference guide
- [`LICENSE.txt`](LICENSE.txt) — the project license
