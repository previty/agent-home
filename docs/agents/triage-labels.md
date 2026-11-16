# Triage labels

Jira has no triage labels for this project. Triage state is the Jira status. This file maps each canonical triage role to the status that represents it in project `CHECK`.

| Role | Jira status | Notes |
|---|---|---|
| `needs-triage` | `Zu erledigen` for bugs, `Bereit` for every other work type | Split by work type: `Zu erledigen` is used for bugs only |
| `needs-info` | `Ready for Planning` | |
| `ready-for-agent` | `Ready for Dev` | Not yet distinguished from `ready-for-human`, because the team develops in tandem |
| `ready-for-human` | `Ready for Dev` | Same status as `ready-for-agent` for now |
| `wontfix` | `Geschlossen` | Shared with "done". The closing comment must say it's a won't-do |

## Statuses that are not triage roles

- `Blocked`: deferred because it depends on something else. Blocking links between tickets are Jira issue links, not this status.
- `Started`: being worked on.
- `Wird überprüft`: in review.

When a skill mentions a role (e.g. "apply the ready-for-agent triage label"), set the Jira status from the table above.
