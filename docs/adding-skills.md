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

`skills/saas-planning-baseline/` preserves the existing `SKILL.md` name and `$saas-planning-baseline` trigger from `deslopified-kit/deslopified-skill/`. To rebrand (e.g. `deslopified-baseline`):
- rename folder + `name:` field together,
- update `agents/openai.yaml` `default_prompt` and any `$...` references in docs.
