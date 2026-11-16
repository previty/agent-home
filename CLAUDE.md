# Previty Check

AI-assisted compliance checking. This is the home repo for coding agents: it holds what is
true across repos. Each repo below is its own git repo; develop, test and deploy per repo,
and read its own `CLAUDE.md` before working in it.

## Repos

All repos, this one included, sit side by side in one folder. If one is missing, clone it
from `github.com/previty/<repo>`. Local clones can be stale: `git fetch` before relying on
them. Ignore folders not listed here unless asked.

| Repo | Role |
|---|---|
| `infrastructure` | OpenTofu/AWS backbone; the services' deploy workflows consume its outputs |
| `check-frontend` | React/Vite UI; talks only to `workspace-service` |
| `design-system` | `@previty/*` packages (tokens, assets, components) used by `check-frontend` |
| `workspace-service` | FastAPI backend: applications, policy sets, compliance checks, organizations; dispatches check jobs via SQS |
| `agentic-check-service` | Continuous SQS consumer that runs compliance checks and reports back to `workspace-service` |
| `local-infra-dev` | Docker Compose: Postgres + LocalStack (S3, SQS) |
| `agent-benchmark` | Local prototype of the check workflow; not deployed |
| `docs` | Glossary, PRDs, RFCs, ADRs |
| `policy-ingestion-service`, `policy-extraction-service` | Legacy; ignore unless asked to work on them |

`workspace-service` and `agentic-check-service` share the S3 buckets `graphs`, `policy-sets`
and `data-sources` (env-prefixed when deployed).

## Development
- Branch from latest `dev` as `feature/<JIRA-ID>-<kebab-title>`; on `main` or `dev`, ask for
  a branch name first. PR into `dev`. If a repo has no `dev`, branch from and PR into `main`.
- Conventional Commits with a scope. Git hooks run the checks on push; never skip them with
  `--no-verify` unless the user says so.
- No Jira IDs in code comments: explain the why in the comment, or point to an ADR.
- Don't commit plans or specs for small changes; only larger work gets a PRD/RFC/ADR in `docs`.
- Python repos: `cd <repo> && uv run ...`.
- Never commit `.env` files or tokens. AWS: only the user can `aws login`; ask them to.

## Agent skills
- Issue tracker: Jira project `CHECK` via the Atlassian MCP. See `docs/agents/issue-tracker.md` in agent-home.
- Triage: Jira statuses stand in for triage labels. See `docs/agents/triage-labels.md` in agent-home.
- Domain: one `GLOSSARY.md` and the ADRs live in the `docs` repo. See `docs/agents/domain.md` in agent-home.
- Design docs: `README.md` in the `docs` repo. Only larger changes need an ADR; if one exists
  for the work, implement only after it is Accepted.
- The team skills are the `previty` plugin in `plugins/previty/` of agent-home. Read its
  `SOURCE.md` before changing a skill.
