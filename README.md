# Linux Terminal Reference — 250+ Commands, Concepts & Recipes

A practical Linux terminal reference for sysadmins, developers, and advanced users.

**→ [Open the full reference](linux-terminal-commands.md)**

---

## What's inside

The full reference is organized into 25+ sections:

**Foundations**
- Command discovery & help
- Files & directory management
- Viewing & editing files
- Text processing & data transformation
- Pipelines & redirection

**System administration**
- Permissions & ownership
- Users & groups
- Processes & job control
- System & performance monitoring
- Storage & filesystems
- systemd, services & logs
- Package managers
- Hardware & kernel inspection

**Networking**
- Networking diagnostics & transfer

**Shell mastery**
- Shell environment & builtins
- Shell scripting basics
- Shell shortcuts, history & globbing
- Aliases & functions

**Developer tooling**
- Executables, libraries & binary inspection
- Checksums & integrity
- Archives & compression
- Version control & development utilities
- Terminal multiplexing & modern replacements (`rg`, `fd`, `fzf`, `eza`…)

**In practice**
- Practical troubleshooting workflow
- Practical recipes (backups, log monitoring, port ownership…)
- Security & safety rules
- Quick safety summary
- Terminal fun & eye candy

---

## Legend

| Marker | Meaning |
|---|---|
| 🟢 | Safe — normally read-only or low-risk |
| 🟡 | Caution — changes state/configuration but is usually recoverable |
| 🔴 | Destructive — can delete, overwrite, repartition, or seriously damage data |
| 🔐 | sudo — commonly requires elevated privileges |
| 🌍 | Not universal — distro/package-dependent |
| 💡 | Tip — useful shortcut or best practice |

---

## Safety first

- Before unfamiliar commands, try `command --help`, then `man command`.
- Preview destructive operations first: `tar -tf`, `unzip -l`, `ls *.log` before `rm`.
- Destructive tools (`dd`, `mkfs`, `fdisk`, `fsck`, `rm -rf`) get 🔴 markers plus a caution note.
- Availability and exact options vary by distro, shell, and installed packages.

**If you don't know what a command does, don't guess.**

---

## Repository layout

| File | Purpose |
|---|---|
| [`linux-terminal-commands.md`](linux-terminal-commands.md) | The full, canonical reference |
| [`linux_commands_reference.md`](linux_commands_reference.md) | Legacy early draft — superseded, kept for history |

## Contributing

Content changes go to [`linux-terminal-commands.md`](linux-terminal-commands.md), not this README:

- Keep sequential row numbering across tables in the reference.
- Add the appropriate markers (🟢 🟡 🔴 🔐 🌍 💡) to new rows.
- Avoid wording that assumes a specific distro; use 🌍 instead.
- Prefer safe previews (`ls`, `tar -tf`) over destructive examples.