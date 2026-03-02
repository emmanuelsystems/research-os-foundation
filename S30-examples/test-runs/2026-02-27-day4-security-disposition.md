# Day 4 Security Disposition

- **Date:** 2026-03-02
- **Scope:** Day 4 Block 3 warning disposition
- **Owner:** ops-team
- **Status:** draft for reviewer signoff

## Warning Disposition Table
| Check ID | Severity | Disposition | Owner | Due Date | Rationale |
|---|---|---|---|---|---|
| `gateway.trusted_proxies_missing` | warn | accepted risk (conditional) | ops-team | 2026-03-09 | Current gateway bind is loopback-only; no reverse proxy exposure in current topology. Must be fixed before any proxied/public Control UI exposure. |
| `gateway.nodes.deny_commands_ineffective` | warn | fix now | ops-team | 2026-03-03 | Exact-name matching means ineffective deny entries do not enforce intended restrictions. Immediate config alignment reduces control-plane risk. |

## Immediate Actions
1. Update `gateway.nodes.denyCommands` to exact supported command names and verify with `openclaw security audit --json`.
2. Keep gateway/UI local-only until trusted proxy configuration is explicitly implemented and documented.
3. Re-run `openclaw doctor` after denyCommands fix and record delta in next hardening snapshot.

## Residual Risk
- Residual risk is acceptable for local-loopback operation only.
- Risk is not acceptable for reverse-proxied/public exposure until trusted proxies are configured.
