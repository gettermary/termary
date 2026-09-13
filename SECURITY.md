# Security Policy

## Reporting a vulnerability

**Do not open a public issue.** Email **security@termary.com** instead.

Please include what you were able to do, the steps to reproduce it, and the version and
platform you were on. A proof of concept helps but is not required to report something.

You should get an acknowledgement within 3 working days. We'll tell you what we found,
what we're doing about it, and when it ships. If you'd like credit in the release notes,
say so and we'll include you.

Please give us reasonable time to ship a fix before disclosing publicly.

## Supported versions

The latest release of each platform. Fixes are not backported.

## What's worth looking at

Termary is a terminal that agents can drive and that a phone can steer remotely, so its
attack surface is larger than a typical editor's. Areas of genuine interest:

- **The local bridge** — an HTTP server on loopback, used by the bundled MCP server and
  by paired phones. Auth is a per-session bearer token or a paired-device token.
- **Device pairing** — a 6-digit code with a short TTL mints a per-device token. The
  desktop stores only a SHA-256 of it.
- **Remote access** — an optional cloudflared tunnel exposes the bridge publicly. The
  device token is still required, but the transport is not yet end-to-end encrypted.
- **The dev-server proxy** — a cookie-routed reverse proxy that splices requests to
  `127.0.0.1:<port>`.
- **The control lock** — which paired device may send input. Note this is an anti-sharing
  and UX boundary; the real security boundary is the per-device token.
- **Anything that executes** — `/panes/open` `on_start`, `/panes/split`, `browser/eval`.

## Known limits (please don't report these as findings)

- **Traffic between a phone and the desktop is TLS-encrypted but not end-to-end.** A
  relay or tunnel provider terminates TLS and can in principle see terminal bytes. E2E
  is designed and not yet shipped; we don't claim otherwise anywhere in the product.
- **The desktop app is unsandboxed.** It has to spawn shells.
- **Windows and Linux builds are currently unsigned.**
