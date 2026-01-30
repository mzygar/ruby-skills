# Agents

This repository includes two local skills. Load them only when the task matches the scope described below.

## ror-better-specs (betterspecs-skill/SKILL.md)

Load when the user asks to write, review, refactor, or teach Rails/RSpec specs, or when they request Better Specs rules/checklists or examples.

- Open `betterspecs-skill/SKILL.md` and follow its workflow.
- Load only the rule files under `betterspecs-skill/rules/` that match the question.

## ror-styleguide (ror-styleguide/SKILL.md)

Load when the user asks to apply, summarize, or enforce Rails style conventions for configuration, routing, controllers, models, migrations, views, i18n, assets, mailers, Active Support, time/duration, bundler, testing, or process management.

- Open `ror-styleguide/SKILL.md` and follow its workflow.
- Load only the relevant section files under `ror-styleguide/references/` for the areas in scope.

## When not to load a skill

- If the request does not involve Rails/RSpec specs or Rails style rules, proceed without loading a skill.
- If the user explicitly asks to avoid using skills, comply.
