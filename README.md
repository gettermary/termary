<h1 align="center">Termary</h1>

<p align="center">
  A native terminal built for working with AI coding agents —<br>
  multi-pane, multi-group, and watchable from your phone.
</p>

<p align="center">
  <a href="https://termary.com">Website</a> ·
  <a href="https://github.com/gettermary/termary/releases">Releases</a> ·
  <a href="https://github.com/gettermary/termary/issues/new/choose">Report an issue</a>
</p>

---

This repository is where Termary's **bug reports, feature requests and releases** live.
The application source is not here.

## Download

| Platform | |
|---|---|
| macOS | [Latest release](https://github.com/gettermary/termary/releases/latest) |
| Windows | [Latest release](https://github.com/gettermary/termary/releases/latest) — `.msi` or portable `.zip` |
| Linux | [Latest release](https://github.com/gettermary/termary/releases/latest) — `.AppImage` or `.tar.gz` |
| iOS | TestFlight (companion app — requires a Mac running Termary) |

## What it does

- **Panes and groups** that survive restarts — split, move, swap; sessions restore with their scrollback
- **Agent-aware** — Termary knows when Claude Code or Codex is working, needs you, or has finished, and says so on the tab, the dock and your phone
- **Your phone as the second screen** — watch a live terminal mirror, answer a permission prompt, reply by voice
- **Browser pane + MCP bridge** — agents can drive a real browser and read back console, network and DOM

## Reporting a bug

Please use the [issue templates](https://github.com/gettermary/termary/issues/new/choose).
The fields there aren't bureaucracy — agent-detection bugs are usually specific to one
CLI version, and networking bugs behave differently on LAN versus tunnel, so those
answers are what make a report actionable.

## Security

Termary runs a local HTTP bridge, can open a public tunnel, and allows remote control of
a development machine. Please report vulnerabilities privately — see [SECURITY.md](SECURITY.md).
Do not open a public issue for a security problem.
