# Optidigi Skills

Central home for reusable agent skills. Each skill is a self-contained folder under `skills/<skill-name>/` following the Agent Skills spec (`SKILL.md` + co-located assets).

## Skills

| Skill | Path | Purpose |
|---|---|---|
| `build-ready-baseline` | `skills/build-ready-baseline/` | Create/revise a SaaS product-planning baseline + engineering handoff. Discovery, initial architecture, feasibility, planning refresh — not ordinary coding. |

> Naming: `skills/build-ready-baseline/` matches `SKILL.md` frontmatter `name` and the `$build-ready-baseline` trigger. Source was `deslopified-kit/deslopified-skill/` (`saas-planning-baseline`).

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
