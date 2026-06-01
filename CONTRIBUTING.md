# Contributing to squadrunner-sandbox

This repo is the shakedown backlog for the **Mission Control** squad running under the [SquadRunner](https://github.com/ashburn-young/SquadRunner) pattern. The notes below explain how to file work so the squad runner picks it up automatically.

---

## Filing work for the squad

1. **Open a GitHub Issue** in this repo describing the work.
2. Add the `squad` label — this is the gate label that tells the squad runner the issue is ready to dispatch.
3. Add a priority label (see below).
4. Optionally add a `squad:<member>` routing label to assign the issue directly to a member (see `.squad/team.md`). Without it, the issue falls back to **Flight** for triage.

The `squad watch` process polls every 5 minutes and will pick up any issue carrying the `squad` label.

---

## Labels

### Priority labels

| Label | Meaning |
|-------|---------|
| `priority:P0` | Critical — jumps the queue immediately |
| `priority:P1` | High — next in line |
| `priority:P2` | Normal — standard queue order |
| `priority:P3` | Low — background work |

### Routing labels

Add `squad:<member>` to route directly to a specific Mission Control member. The available members and their specialisations are listed in [`.squad/team.md`](.squad/team.md) and [`.squad/routing.md`](.squad/routing.md).

Examples:

| Label | Routed to |
|-------|-----------|
| `squad:handbook` | Handbook — docs & usability |
| `squad:eecom` | EECOM — core implementation |
| `squad:booster` | Booster — CI/CD |
| `squad:flight` | Flight — architecture (also the default fallback) |

---

## PR review flow

1. The squad runner opens a **draft PR** from the working branch into `main`.
2. A human reviewer inspects the diff and either approves, requests changes, or closes.
3. The runner never merges without human approval — draft PRs stay draft until a maintainer promotes them.

If the runner hits a blocker it cannot resolve, it will comment on the issue explaining what is needed and move on to the next item.

---

## Questions?

See the [`README.md`](README.md) for an overview of how the squad runner works end-to-end.
