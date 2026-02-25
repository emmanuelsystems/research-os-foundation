# OpenClaw Gateway Token Repair (Windows)

- **Date:** 2026-02-25
- **Status:** actionable
- **Issue:** Control UI websocket unauthorized (`1008 token_missing`) and intermittent `EPERM` on `~/.openclaw/identity/device-auth.json`.

## What This Means
1. Control UI is connecting without a valid gateway token.
2. In some shells/runs, OpenClaw cannot read `device-auth.json` (permission context mismatch).

## Recovery Steps (In Order)
1. Stop stale gateway listeners:
   - `openclaw gateway stop`
2. Start gateway in foreground with force (single owner process):
   - `openclaw gateway run --force`
3. In a second terminal, get tokenized Control UI URL:
   - `openclaw dashboard --no-open`
4. Open the exact URL that includes `#token=...` (do not use plain `/` URL).
5. If UI already open, hard refresh and re-open only tokenized URL.
6. Verify:
   - `openclaw status`
   - expect gateway `reachable` and no `token_missing` websocket errors.

## Verified Recovery Signal (2026-02-25)
- Before restart: `Invoke-WebRequest http://127.0.0.1:18789/` -> `Unable to connect to the remote server`
- After starting gateway process: `Invoke-WebRequest http://127.0.0.1:18789/` -> `200`
- Port check after restart: `netstat -ano | findstr LISTENING | findstr :18789` shows active listeners on `127.0.0.1:18789` and `[::1]:18789`.

## If EPERM Persists
1. Run the same commands from an elevated PowerShell (Run as Administrator).
2. Ensure only one Windows user/session is managing `C:\Users\CREATIVES\.openclaw\`.
3. Check file read permissions on:
   - `C:\Users\CREATIVES\.openclaw\identity\device-auth.json`
4. Re-run:
   - `openclaw doctor --fix`
   - `openclaw status --all`

## Validation Checklist
- [ ] `openclaw gateway run --force` starts cleanly.
- [ ] Control UI opened using tokenized URL from `openclaw dashboard --no-open`.
- [ ] No `1008 token_missing` in logs during UI connection.
- [ ] `openclaw status` shows gateway reachable.
- [ ] Slack channel remains `ON / OK`.

## Notes
- `openclaw dashboard --no-open` returns the canonical URL for the current token; use it each time after gateway restarts.
- Do not store gateway token in repo files or screenshots shared publicly.
- If a token is exposed, rotate it immediately:
  - `openclaw devices rotate`
