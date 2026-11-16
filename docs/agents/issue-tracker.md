# Issue tracker: Jira

Issues for the Previty Check platform live in Jira: <https://previty.atlassian.net>, project key `CHECK`. Jira is the only tracker. Nothing is mirrored into local files.

Access goes through the Atlassian MCP tools (provided by the `atlassian` plugin). Use cloudId `2fd3f449-cbea-429f-987d-1e6a5f36207b`.

## Conventions

- **Create an issue**: `createJiraIssue` in project `CHECK`. Work types: Task, Bug, Story, Epic, Sub-task.
- **Read an issue**: `getJiraIssue` for one key (e.g. `CHECK-123`). Use view `evidence` to get custom fields.
- **Comments**: read with `listJiraIssueComments`, write with `addOrEditJiraIssueComment`.
- **Search**: `searchJiraIssuesUsingJql`. Quote the project key in JQL, because `CHECK` is a reserved word, e.g. `project = "CHECK" AND status = "Ready for Dev"`.
- **Change status**: `listJiraIssueTransitions` first, then `transitionJiraIssue`. Match the target status, not the transition name.
- **Edit fields**: `editJiraIssue`.
- **Blocking**: Jira issue links (the "Blocks" link type). Confirm the exact link type name the first time it's used.
- **Close**: add the closing reason as a comment, then transition the issue to `Geschlossen`.

## Statuses (project CHECK)

| Status | Category | Meaning |
|---|---|---|
| Zu erledigen | To Do | New bugs (triage state for bugs) |
| Bereit | To Do | New work of every other type (triage state for them) |
| Ready for Planning | To Do | Ready to be planned. Used as the `needs-info` triage state |
| Ready for Dev | To Do | Specified and ready to build |
| Started | In Progress | Being worked on |
| Wird überprüft | In Progress | In review |
| Blocked | To Do | Deferred: depends on something else |
| Geschlossen | Done | Done, or won't do |

See [triage-labels.md](./triage-labels.md) for how the triage roles map onto these statuses.

## Pull requests as a triage surface

No. Jira doesn't receive pull requests, so external PRs are not part of triage.

## When a skill says "publish to the issue tracker"

Create a Jira issue in project `CHECK` with `createJiraIssue`. Use the work type that fits, and start it in the `needs-triage` status for that work type.

## When a skill says "fetch the relevant ticket"

Call `getJiraIssue` with the key, e.g. `CHECK-123`, and `listJiraIssueComments` for the discussion.

## Wayfinding operations

Not configured for Jira yet. Decide how the map and its children are represented before using `/wayfinder`.
