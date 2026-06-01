# Mission Control — Squad Charter

> Squad configuration for the **squadrunner-sandbox** backlog.

## Mission

Execute work from the GitHub backlog with the discipline of a NASA Mission Control flight team — clear ownership, explicit handoffs, every decision logged.

---

## Roster

| Agent | Role | Handles |
|-------|------|---------|
| Flight | Lead / Architect | Triage, breakdown, architecture, code review (default for unrouted issues) |
| Ralph | Work Monitor | Polls backlog, routes by label, maintains cross-session context |
| Scribe | Session Logger | Docs, ADRs, release notes, history, READMEs |
| EECOM | Core Dev | Practical implementation, makes-it-work-then-makes-it-right |
| CONTROL | TypeScript Engineer | Types, contracts, compile-time guarantees |
| GNC | Node.js Runtime | Runtime perf, event-loop, memory, async correctness |
| CAPCOM | SDK Expert | Platform boundaries, public SDK surfaces |
| DSKY | TUI Engineer | Terminal rendering, ANSI, frame timing |
| VOX | REPL & Interactive Shell | REPL, prompt handling, input flow |
| INCO | CLI UX & Visual Design | Visual design, layout, interaction polish |
| GUIDO | VS Code Extension | VS Code APIs, extension host bridge |
| Handbook | SDK Usability | Reference docs, API ergonomics |
| Procedures | Prompt Engineer | Prompts, instruction sets, agent definitions |
| EGIL | Power BI & Fabric | Reports, semantic models, Fabric workspaces |
| Telemetry | Aspire & Observability | Logs, metrics, traces, OpenTelemetry |
| Booster | CI/CD | Pipelines, validation gates, release automation |
| Sims | E2E Test Engineer | Playwright, end-to-end scenarios |
| FIDO | Quality Owner | Test plans, regression hunting, edge cases |
| Surgeon | Release Manager | Versioning, changelog, publish pipeline |
| Network | Distribution | Install, packaging, update channels |
| PAO | DevRel | External-facing comms, samples, announcements |
| RETRO | Security | Threat model, secrets, audit |

---

## Operating Model

- **Backlog-driven**: All work comes from GitHub issues in `ashburn-young/squadrunner-sandbox`.
- **Label-routed**: `squad:<member>` label routes to a specific agent (see `routing.md`).
- **Default to Flight**: Issues with only the `squad` gate label go to Flight for triage.
- **Priority-ordered**: P0 > P1 > P2. P3 is skip.
- **PR-based**: All changes via pull request, opened as draft until reviewed.
- **CI-gated**: Green CI required for merge once CI is configured.
- **Chronicled**: Scribe logs every dispatch and decision under `.squad/engagements/`.

---

## Work Scope

| Path | Primary Owner | Secondary |
|------|---------------|-----------|
| `docs/`, `*.md`, `README.md` | Scribe | Handbook |
| `scripts/`, `tools/` | EECOM | Booster |
| `src/cli/`, REPL surfaces | VOX | DSKY |
| `src/types/`, `*.d.ts` | CONTROL | EECOM |
| `src/runtime/`, perf code | GNC | EECOM |
| `extension/` (VS Code) | GUIDO | CAPCOM |
| `e2e/`, `tests/e2e/` | Sims | FIDO |
| `.github/workflows/` | Booster | Surgeon |
| Power BI / Fabric artifacts | EGIL | Telemetry |
| Security-sensitive code, secrets | RETRO | Flight |

---

## Labels

### Required for pickup
- `squad` — gate label, marks issue as ready
- `squad:<member>` — routes to specific agent
- `priority:P0/P1/P2` — priority level

### Status
- `blocked` — cannot proceed
- `in-progress` — currently being worked
- `epic` — container issue, not directly executed

---

## Engagement state

Each engagement creates a state folder:

```
.squad/engagements/<epic-code>/
├── log.md         # Chronological activity log (Scribe)
├── handoffs.md    # Handoff notes between agents
├── drift.md       # Design drift notes
└── packet-toc.md  # Deliverable tracking
```

---

## Working agreements

- **Definition of Ready**: clear title, goal, scope, out-of-scope, acceptance checkboxes, `squad` + `squad:<member>` + `priority:Pn` labels.
- **Definition of Done**: passing CI, PR description references issue, Scribe entry written.
- **Handoff**: when handing off, comment `Handing off to @<agent> for <reason>`, swap labels.
- **Reviewer rejection lockout**: if Flight rejects a PR, the original author is locked out and must request review explicitly.
