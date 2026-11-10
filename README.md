# task-tracker releases

Download builds of `task-tracker`, a task tracker for the terminal. Each Ticket is a Markdown file you can edit, and
optional Sync keeps your Tickets end-to-end encrypted. The source is private; this repository holds only the release
archives.

Get them from [Releases](https://github.com/Lanskask/terminal-task-tracker-releases/releases/latest).

## Install

### macOS and Linux

One command picks the archive for your system (Intel or Apple silicon, x86_64 or arm64):

```bash
curl -fsSL https://github.com/Lanskask/terminal-task-tracker-releases/releases/latest/download/task-tracker_$(uname -s)_$(uname -m).tar.gz | tar -xz
sudo mv task-tracker /usr/local/bin/
task-tracker init --create-local-tickets
task-tracker
```

On macOS, a binary downloaded with a browser is blocked as "cannot be verified" because it is not signed yet. Use the
`curl` command above, or clear the flag: `xattr -d com.apple.quarantine task-tracker`.

### Windows

1. Download `task-tracker_Windows_x86_64.zip` (or `_arm64.zip`) from
   [Releases](https://github.com/Lanskask/terminal-task-tracker-releases/releases/latest).
2. Unzip it and put `task-tracker.exe` in a folder on your `PATH`.
3. In a terminal, run `task-tracker init --create-local-tickets`, then `task-tracker`.

## Files in each release

| File                                | For                         |
| ----------------------------------- | --------------------------- |
| `task-tracker_Darwin_arm64.tar.gz`  | macOS, Apple silicon        |
| `task-tracker_Darwin_x86_64.tar.gz` | macOS, Intel                |
| `task-tracker_Linux_x86_64.tar.gz`  | Linux, x86_64               |
| `task-tracker_Linux_aarch64.tar.gz` | Linux, arm64                |
| `task-tracker_Windows_x86_64.zip`   | Windows, x86_64             |
| `task-tracker_Windows_arm64.zip`    | Windows, arm64              |
| `checksums.txt`                     | SHA-256 of every file above |

Check a download: `shasum -a 256 -c checksums.txt --ignore-missing` (macOS and Linux).

## Sync and the web app

Optional. Create an account with `task-tracker signup --email you@example.com`.

## How releases get here

A version tag (`v0.1.0`) in the private source repository builds all six archives and publishes the same release here.
Nothing is uploaded by hand.

## License

Proprietary. Copyright © 2026 Lanskask. All rights reserved.
