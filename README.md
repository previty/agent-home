# agent-home

Home repo for the coding agents that work on Previty's repositories. It holds what is
true across repos: the shared CLAUDE.md, the team skills plugin, and guidance on where
project knowledge belongs.

What is true of one repo alone stays in that repo's own CLAUDE.md.

## Setup

1. Clone this repo next to the other Previty repos.
2. Install the team skills once; they then work in every repo:

   ```bash
   claude plugin marketplace add previty/agent-home
   claude plugin install previty@agent-home
   ```

   Claude Code fetches the plugin with your own git credentials, e.g. after
   `gh auth login && gh auth setup-git`.
3. For work that spans repos, start Claude Code here (`cd agent-home && claude`) and trust the
   folder. The session can read and edit the neighbouring repos. For single-repo work, start in
   that repo as before.

## Layout

- `CLAUDE.md`: shared instructions and a pointer to every repo
- `docs/agents/`: how skills use Jira, triage statuses, the glossary and ADRs
- `plugins/previty/`: the team plugin; `SOURCE.md` says where its skills come from
- `.claude-plugin/marketplace.json`: makes this repo a Claude Code marketplace
