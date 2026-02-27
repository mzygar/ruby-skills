---
name: rails-upgrade-latest
description: Rails upgrade workflow for moving an existing application to the latest stable Rails release using the official upgrade guide. Use when planning or executing Rails version migrations, resolving deprecations, updating framework defaults, running `rails app:update`, or coordinating safe stepwise upgrades across multiple minor/major versions with verification gates.
---

# Rails Upgrade Latest

Use this skill to execute Rails upgrades with predictable checkpoints and minimal downtime risk.

## Workflow

1. Confirm baseline and target:
- Detect current Rails/Ruby versions from `Gemfile.lock`, `ruby -v`, and `bin/rails -v`.
- Determine the latest stable Rails target and required Ruby version.
- If the jump spans multiple versions, upgrade one minor/major step at a time.

2. Read the upgrade references:
- Open `references/upgrade-workflow.md` and follow the sequence.
- For each version jump, read that version's release notes before changing code.

3. Prepare safety rails:
- Ensure branch isolation and clean git status.
- Ensure strong test coverage for core user flows before version changes.
- Remove or update unsupported/deprecated gems first.

4. Upgrade incrementally:
- Bump Rails and related gems in `Gemfile`.
- Run `bundle update rails` (and related railties gems as needed).
- Run `bin/rails app:update`; review every diff instead of accepting blindly.
- Keep old framework defaults in place during each jump, then enable new defaults gradually.

5. Resolve breakages and deprecations:
- Fix boot/runtime errors and then failing tests.
- Address deprecation warnings proactively to reduce next-step breakage.
- Upgrade config, initializers, autoloading, Active Storage, and Action Cable settings when required by the guide/release notes.

6. Run mandatory quality gates:
- Run `bundle exec rspec`; do not finish while any spec fails.
- Run `bundle exec rubocop`; do not finish while offenses remain.
- If either fails, fix issues and rerun both commands until both are green in the same state.

7. Finalize:
- Summarize changed files, migration notes, and any required follow-up tasks.
- Call out remaining risk areas explicitly (for example: untested paths or temporarily retained legacy defaults).

## Required Behaviors

- Prefer smallest safe change set per version step over big-bang upgrades.
- Never skip release notes for the exact target version.
- Never claim completion unless both `bundle exec rspec` and `bundle exec rubocop` pass.
- If a project cannot run one of those commands, state the blocker and the exact missing prerequisite.

## Reference Map

- `references/upgrade-workflow.md`: Rails-guide-aligned checklist, command sequence, and per-version validation points.
