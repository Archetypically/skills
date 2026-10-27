# AGENTS.md

Notes for any agent working in this repository.

## Commits

- Use Conventional Commits for every commit message: `type(scope): summary`.
- Use one of these types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`.
- Set the scope to the skill name when a change touches one skill, as in `feat(x-virality): add pre-launch checklist`. Leave the scope out for repo-wide changes.
- Write the summary in lowercase imperative form, keep it under 72 characters, and end it without a period.
- Mark a breaking change with `!` after the type or scope, as in `feat(x-virality)!: rename the skill folder`, and explain the break in the commit body.

## Layout

- Keep each skill in its own folder under `skills/`, with its `SKILL.md` as the entry point.
- Give every skill a `README.md` in its folder, written for people rather than agents. It carries the skills.sh badge (`[![skills.sh](https://skills.sh/b/Archetypically/skills)](https://skills.sh/Archetypically/skills)`), the install instructions for that skill, and any credits for source material.
- Keep `SKILL.md` as the agent-facing method only. Credits and install steps do not belong in it.
- Put a skill's supporting material in a `references/` folder inside that skill's folder.
- Give every new skill a row in the README skills table in the same commit that adds it.
