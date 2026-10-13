# Adding / maintaining skills

## Add a new skill

1. Create `skills/<skill-name>/` — lowercase-hyphen, matches `SKILL.md` frontmatter `name:`.
2. Add `SKILL.md` with frontmatter:
   ```yaml
   ---
   name: <skill-name>
   description: >-
     What it does, when to use it, and what it explicitly does NOT do.
   ---
   ```
3. Keep assets co-located: `assets/`, optional `references/`, `scripts/`.
4. Reference assets with relative links only (`assets/foo.md`).
5. Update root `README.md` skills table.
6. Run validation: `python3 scripts/validate.py` (or CI).

## Conventions

- One skill = one folder, self-contained. No cross-skill relative imports.
- Descriptions state trigger + non-goals (prevents mis-firing).
- Host-specific metadata (`agents/openai.yaml`) is optional legacy — keep only if a host needs it.
- Companion guides/playbooks that are not agent instructions go in `docs/`, not inside `skills/`.

## Current naming decision

`skills/build-ready-baseline/` (frontmatter `name: build-ready-baseline`, trigger `$build-ready-baseline`). Migrated from `deslopified-kit/deslopified-skill/` (formerly `saas-planning-baseline`). Folder + `name:` must stay in sync; `agents/openai.yaml` `default_prompt` follows the same trigger.
