# Skill source

The skills in `skills/` are copied from https://github.com/mattpocock/skills (MIT, see
`LICENSE-mattpocock-skills`) and shipped as the team plugin `previty`. They replace Matt's own
`mattpocock-skills` plugin; don't install both, or every skill exists twice.

- **Upstream commit:** `4ae2317ddb22b046e26455e4f9c9b3aaaf62212d` (2026-10-31)
- **Copied from:** `skills/engineering/` (20) and `skills/productivity/` (7)
- **Not copied:** each skill's `agents/openai.yaml` (Codex-only metadata), and the `misc/`,
  `in-progress/` and `deprecated/` buckets
- **Changed here:** `ask-matt`, `retro` and `writing-for-agents` say `CLAUDE.md` where
  upstream says `AGENTS.md`. The other 24 match upstream.

## Updating

1. Clone the upstream repo and check out the commit you want.
2. Compare each folder here with its upstream counterpart, skipping `agents/`.
3. Copy the changed files over, keeping the changes listed above, then update the commit hash
   above.

The plugin has no `version` on purpose: every commit to `main` is an update.
