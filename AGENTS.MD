# Agents

This repository includes three local skills. Load them only when the task matches the scope described below.

## ror-better-specs (betterspecs-skill/SKILL.md)

Load when the user asks to write, review, refactor, or teach Rails/RSpec specs, or when they request Better Specs rules/checklists or examples.

- Open `betterspecs-skill/SKILL.md` and follow its workflow.
- Load only the rule files under `betterspecs-skill/rules/` that match the question.

## ror-styleguide (ror-styleguide/SKILL.md)

Load when the user asks to apply, summarize, or enforce Rails style conventions for configuration, routing, controllers, models, migrations, views, i18n, assets, mailers, Active Support, time/duration, bundler, testing, or process management.

- Open `ror-styleguide/SKILL.md` and follow its workflow.
- Load only the relevant section files under `ror-styleguide/references/` for the areas in scope.

## rails-upgrade-latest (rails-upgrade-latest/SKILL.md)

Load when the user asks to upgrade or migrate an existing Rails app to a newer/latest Rails version, or requests a Rails upgrade checklist/workflow based on the official upgrading guide.

- Open `rails-upgrade-latest/SKILL.md` and follow its workflow.
- Load `rails-upgrade-latest/references/upgrade-workflow.md` for the guide-aligned step-by-step checklist.

## When not to load a skill

- If the request does not involve Rails/RSpec specs, Rails style rules, or Rails version upgrades, proceed without loading a skill.
- If the user explicitly asks to avoid using skills, comply.
