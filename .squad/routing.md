# Routing Rules

> Label-based routing for Mission Control squad agents.

## Default routing

Issues that carry the `squad` gate label but **no** `squad:<member>` label are routed to **Flight** for triage. Flight assigns the appropriate `squad:<member>` label and (if needed) breaks the issue into smaller children.

## Member routes

| Label | Routes to | Handles |
|---|---|---|
| `squad:flight` | Flight | Triage, architecture, scope decisions |
| `squad:ralph` | Ralph | Polling, routing logic, cross-session memory |
| `squad:scribe` | Scribe | Docs, ADRs, READMEs, history |
| `squad:eecom` | EECOM | Core implementation |
| `squad:control` | CONTROL | TypeScript types, contracts |
| `squad:gnc` | GNC | Node runtime, perf, async correctness |
| `squad:capcom` | CAPCOM | SDK boundaries |
| `squad:dsky` | DSKY | TUI / terminal rendering |
| `squad:vox` | VOX | REPL, interactive shell |
| `squad:inco` | INCO | CLI UX, visual design |
| `squad:guido` | GUIDO | VS Code extension |
| `squad:handbook` | Handbook | SDK reference docs |
| `squad:procedures` | Procedures | Prompts, agent definitions |
| `squad:egil` | EGIL | Power BI / Fabric |
| `squad:telemetry` | Telemetry | Logs, metrics, traces |
| `squad:booster` | Booster | CI/CD pipelines |
| `squad:sims` | Sims | E2E tests |
| `squad:fido` | FIDO | Quality / regression hunting |
| `squad:surgeon` | Surgeon | Releases |
| `squad:network` | Network | Distribution / install |
| `squad:pao` | PAO | DevRel comms |
| `squad:retro` | RETRO | Security |

## Priority order

Within each member's queue:

```
priority:P0 > priority:P1 > priority:P2
```

- **P0** — drop everything
- **P1** — next in queue
- **P2** — standard order
- **P3** — skip (needs human)

## Skip conditions

Do NOT pick up issues that:

- Have `epic` label (container issues)
- Have `blocked` label
- Have `priority:P3` label
- Are in `closed` state
- Lack the `squad` gate label

## Handoff protocol

When handing off to another agent:

1. Complete your portion of work.
2. Comment: `Handing off to @<agent> for <reason>`.
3. Remove your `squad:<member>` label.
4. Add the recipient's `squad:<member>` label.
5. Recipient picks up on next poll cycle.

## Multi-agent issues

Some issues require coordination. Declare in issue body:

```html
<!-- requires: eecom, scribe, booster -->
```

- First-listed agent picks up.
- Hand off to next when ready.
- Last agent closes the issue.

## Escalation

| Condition | Escalate to |
|---|---|
| Architectural ambiguity | Flight |
| Security concern | RETRO |
| CI failure that blocks others | Booster |
| Release-blocking regression | Surgeon + FIDO |
| Any P0 not picked up within one poll cycle | Flight |
