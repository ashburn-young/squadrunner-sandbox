# squadrunner-sandbox

Shakedown backlog for the **Mission Control** squad running under the [SquadRunner](https://github.com/ashburn-young/SquadRunner) pattern.

This repo exists so the squad has a real GitHub backlog to poll, triage, and open PRs against without touching production projects.

## How it works

1. A backlog issue is filed with the `squad` gate label plus a `squad:<member>` route label and a `priority:Pn` label.
2. The `squad watch` process on the SquadRunner VM polls every 5 minutes via `gh`.
3. Ralph picks up the issue, dispatches to the routed Mission Control member, or routes to Flight for triage if no member label is present.
4. The member opens a draft PR against `main` for human review.

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to file work and the PR review flow, `.squad/team.md` for the charter, and `.squad/routing.md` for label rules.

---

## Original README
SquadRunner shakedown sandbox — Mission Control squad runs against this backlog
