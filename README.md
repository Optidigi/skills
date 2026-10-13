# Optidigi Skills

Central home for reusable agent skills. Each skill is a self-contained folder under `skills/<skill-name>/` following the Agent Skills spec (`SKILL.md` + co-located assets).

## Skills

| Skill | Path | Purpose |
|---|---|---|
| `saas-planning-baseline` | `skills/saas-planning-baseline/` | Create/revise a SaaS product-planning baseline + engineering handoff. Discovery, initial architecture, feasibility, planning refresh — not ordinary coding. |

> Naming note (open): local source folder is `deslopified-skill/` but `SKILL.md` frontmatter is `name: saas-planning-baseline`. V1 uses `skills/saas-planning-baseline/` so folder matches frontmatter `name` and existing `$saas-planning-baseline` trigger. Renaming to a branded name (e.g. `deslopified-baseline`) is a one-folder + one-field change if you want it — see `docs/adding-skills.md`.

## Shape

```text
skills/
  <skill-name>/
    SKILL.md              # required: frontmatter name + description, instructions
    assets/               # templates, reference material loaded by the skill
    references/           # (optional) deep docs, loaded on demand
    scripts/              # (optional) executable helpers
    agents/               # (optional, legacy) host-specific metadata, e.g. openai.yaml
README.md
LICENSE
docs/
  adding-skills.md
.github/workflows/validate.yml
```

Rules:
- `skills/<name>/` matches `SKILL.md` frontmatter `name:` (lowercase-hyphen).
- Keep each skill self-contained; relative links only (`assets/...`).
- Companion guides that are not loaded instructions live in `docs/`, not inside a skill.

## Use

Copy `skills/<skill-name>/` into your host's supported skill install path, keeping its files together. Verify the host discovers the intended skill + template. Do not assume a host-specific path in this repo.

## Adding a skill

See `docs/adding-skills.md`.
