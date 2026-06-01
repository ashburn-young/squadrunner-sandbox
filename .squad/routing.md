# Routing Rules

How `squad triage --execute` maps an issue to a Mission Control member.

## Work Type → Agent

| Work Type | Agent | Examples |
|-----------|-------|----------|
| Architecture & Patterns | Flight | architecture, design, system, pattern, refactor strategy |
| Core Dev | EECOM | implementation, refactor, bug fix, core, util |
| TypeScript | CONTROL | typescript, types, tsc, generics, type error, strict |
| Node.js Runtime | GNC | node, event loop, performance, async, stream, memory |
| SDK | CAPCOM | sdk, public api, package boundary, platform |
| TUI & Terminal | DSKY | tui, terminal, ink, render, ansi, color, keystroke |
| REPL | VOX | repl, interactive, shell, prompt, command parser |
| CLI UX | INCO | ux, layout, design, visual, prompt design |
| VS Code Extension | GUIDO | vscode, extension, webview, lsp |
| SDK Docs | Handbook | docs, readme, api reference, manual, usability |
| Prompt Engineering | Procedures | prompt, instruction, llm prompt, system message |
| Power BI & Fabric | EGIL | powerbi, fabric, pbip, dax, semantic model, report |
| Observability | Telemetry | telemetry, metrics, logs, tracing, otel, aspire |
| CI/CD | Booster | ci, cd, pipeline, github actions, build, release workflow |
| E2E Tests | Sims | e2e, end-to-end, simulation, playwright, integration |
| QA & Quality | FIDO | qa, quality, regression, flaky, edge case |
| Release | Surgeon | release, version, changelog, tag, publish |
| Distribution | Network | install, installer, distribution, packaging, registry |
| DevRel | PAO | devrel, blog, evangelism, demo, talk |
| Security | RETRO | security, vulnerability, auth, secrets, dependency cve |

## Module Ownership

| Module | Primary | Secondary |
|--------|---------|-----------|
| .github/workflows/ | Booster | Surgeon |
| docs/ | Handbook | PAO |
| src/cli/ | VOX | INCO |
| src/tui/ | DSKY | INCO |
| src/sdk/ | CAPCOM | CONTROL |
| src/runtime/ | GNC | EECOM |
| test/e2e/ | Sims | FIDO |
| security/ | RETRO | Flight |

## Defaults
- Unlabelled `squad` issues fall back to **Flight** (Lead).
- Priority order: `priority:P0` > `P1` > `P2` > `P3`.
- A pre-assigned `squad:<member>` label always wins over keyword routing.
- `Ralph` and `Scribe` are runtime roles, not routing targets.
