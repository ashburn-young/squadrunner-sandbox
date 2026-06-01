# Mission Control Squad

## Identity
- **Squad:** mission-control
- **Owner:** ashburn-young
- **Repository:** github.com/ashburn-young/squadrunner-sandbox

The 23-member Mission Control squad, adapted from Young Kim's Clawpilot agents
to run autonomously via the SquadRunner pattern (`squad triage --execute` in a
tmux session on an Azure VM).

## Members

| Name | Role | Charter | Status |
|------|------|---------|--------|
| Flight | Lead — Architecture & Patterns | `.squad/agents/flight/charter.md` | ✅ Active |
| Ralph | Work Monitor — Persistent Memory | `.squad/agents/ralph/charter.md` | ✅ Active |
| Scribe | Session Logger — Team Memory | `.squad/agents/scribe/charter.md` | ✅ Active |
| EECOM | Core Dev — Implementation | `.squad/agents/eecom/charter.md` | ✅ Active |
| CONTROL | TypeScript Engineer — Type Contracts | `.squad/agents/control/charter.md` | ✅ Active |
| GNC | Node.js Runtime — Event Loop & Perf | `.squad/agents/gnc/charter.md` | ✅ Active |
| CAPCOM | SDK Expert — Platform Boundaries | `.squad/agents/capcom/charter.md` | ✅ Active |
| DSKY | TUI Engineer — Terminal Rendering | `.squad/agents/dsky/charter.md` | ✅ Active |
| VOX | REPL & Interactive Shell | `.squad/agents/vox/charter.md` | ✅ Active |
| INCO | CLI UX & Visual Design | `.squad/agents/inco/charter.md` | ✅ Active |
| GUIDO | VS Code Extension Engineer | `.squad/agents/guido/charter.md` | ✅ Active |
| Handbook | SDK Usability & Documentation | `.squad/agents/handbook/charter.md` | ✅ Active |
| Procedures | Prompt Engineering | `.squad/agents/procedures/charter.md` | ✅ Active |
| EGIL | Power BI & Fabric — Code-First BI | `.squad/agents/egil/charter.md` | ✅ Active |
| Telemetry | Aspire & Observability | `.squad/agents/telemetry/charter.md` | ✅ Active |
| Booster | CI/CD Engineer | `.squad/agents/booster/charter.md` | ✅ Active |
| Sims | E2E Test Engineer | `.squad/agents/sims/charter.md` | ✅ Active |
| FIDO | Quality Owner — QA | `.squad/agents/fido/charter.md` | ✅ Active |
| Surgeon | Release Manager | `.squad/agents/surgeon/charter.md` | ✅ Active |
| Network | Distribution & Install | `.squad/agents/network/charter.md` | ✅ Active |
| PAO | DevRel — Public Affairs | `.squad/agents/pao/charter.md` | ✅ Active |
| RETRO | Security | `.squad/agents/retro/charter.md` | ✅ Active |

> Note: `Ralph` and `Scribe` are excluded from auto-triage by the squad runtime
> (built-in monitor / logger roles) but remain part of the roster for reference.

## Project Context

Sandbox repository used to validate SquadRunner against Mission Control. Issues
labelled `squad` are picked up by `squad triage --execute` on the VM and routed
to the matching `squad:<name>` member based on `.squad/routing.md`.
