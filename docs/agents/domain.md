# Domain docs

Previty Check is a single context: one glossary covers every repo, so there is no
`GLOSSARY-MAP.md`. All paths below are in the `docs` repo.

- **Glossary**: `GLOSSARY.md` at the root. It is the only glossary. Never create a
  `GLOSSARY.md` in another repo, even when a skill says to create one lazily at the repo root.
- **Feature docs**: `features/CHECK-NNN-kebab-slug/`, holding `prd.md`, optional `rfc.md` and
  `adr.md`. Platform-wide topics go in `platform/`.
- **ADRs**: next to the feature or platform docs they belong to. The registry is
  `adr/README.md`. A number is assigned when the ADR is merged, never while drafting. When a
  skill suggests `docs/adr/NNNN-slug.md`, follow this layout instead.

## Before exploring, read these

- `GLOSSARY.md`.
- The ADRs that touch the area you're about to work in. Find them through `adr/README.md`.

## Use the glossary's vocabulary

When your output names a domain concept (in a Jira issue title, a refactor proposal, a
hypothesis, a test name), use the term as `GLOSSARY.md` defines it. Don't drift to synonyms
the glossary explicitly avoids.

If the concept you need isn't in the glossary yet, either you're inventing language the
project doesn't use (reconsider), or there's a real gap (note it for `domain-modeling`).

## Flag ADR conflicts

If your output contradicts an existing ADR, surface it explicitly rather than overriding it
silently.
