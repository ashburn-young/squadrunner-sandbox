# Contributing to squadrunner-sandbox

This repo runs the **Mission Control** squad via the [SquadRunner](https://github.com/ashburn-young/SquadRunner) pattern. Ralph (the work monitor) picks up issues automatically and routes them to the right squad member.

---

## Filing work for the squad

1. Open a GitHub issue with a clear title and description.
2. Add the `squad` label — this is the dispatch gate. Without it, the runner ignores the issue.
3. Optionally add a `squad:<member>` label (e.g. `squad:handbook`) to route directly to that member. Without one, Flight (Lead) triages and routes it.
4. Add a `priority:P0|P1|P2|P3` label. `P0` jumps the queue; `P3` is backlog.

> See [`.squad/team.md`](.squad/team.md) for the full member roster and [`.squad/routing.md`](.squad/routing.md) for keyword-based routing rules.

---

## Labels

| Label | Purpose |
|-------|---------|
| `squad` | **Required.** Marks an issue for squad pickup. |
| `squad:<member>` | Optional. Forces routing to a named member (e.g. `squad:eecom`). |
| `priority:P0` | Critical — processed immediately. |
| `priority:P1` | High — processed next available cycle. |
| `priority:P2` | Normal — standard queue order. |
| `priority:P3` | Low — backlog, picked up when queue is clear. |

---

## PR review flow

1. Ralph detects the issue and dispatches to the routed squad member.
2. The squad member opens a **draft PR** against `main` with the proposed change.
3. A human reviewer promotes the draft to "Ready for review" and merges.
4. Merging closes the linked issue automatically (include `Closes #N` in the PR body).

Squad members do not merge their own PRs — all merges require human approval.

---

## What not to file here

This is a shakedown sandbox for validating the SquadRunner workflow. Issues should exercise the routing, triage, and PR flow — not production feature work.
