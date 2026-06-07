# RevX Thomas Weekly Summary — Config

## Channels

| Role | Channel |
|------|---------|
| Source | `#revx-thomas` |
| Production destination | `#supplier-new-leads-generation-internalonly` |
| Test destination | DM to requester (Priyanka Verma) |

## Schedule (production automation)

- **When:** Every Monday, 7:00 AM America/New_York
- **Week window:** Previous Sunday 00:00 – Saturday 23:59 ET (week ending yesterday)
- **Automation:** See `AUTOMATION.md` in repo root or `references/automation-prompt.md`

## Modes

| Mode | Default | Destination |
|------|---------|-------------|
| `test` | **Yes** until user says prod | DM to requester |
| `prod` | Only on explicit request | `#supplier-new-leads-generation-internalonly` |

Never post to prod channel during test without explicit confirmation.

## SOW scope

- **Phase 2 (May 2026 onwards):** Primary compliance tracker
- **SOW 1 carryover:** Open items (In Progress, Yet to be Picked) remain on radar
- **Ignore:** Est. Hours column everywhere
