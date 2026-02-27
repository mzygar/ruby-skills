# Rails Upgrade Workflow (Guide-Aligned)

Use this checklist with the official Rails upgrade guide:
https://guides.rubyonrails.org/upgrading_ruby_on_rails.html

## 1) Before changing dependencies

- Confirm current versions:
  - `ruby -v`
  - `bundle exec rails -v` (or `bin/rails -v`)
  - `bundle list | rg '^  \\* rails '`
- Confirm latest stable Rails target and required Ruby version.
- Plan stepwise upgrades if needed (for example, 7.0 -> 7.1 -> 7.2 -> 8.0 -> 8.1).
- Ensure a clean branch and reproducible CI/local test setup.

## 2) Follow official upgrade process sequence

Mirror the guide's core order:

1. Ensure test coverage exists for critical behavior.
2. Update Ruby if required by target Rails.
3. Update `Gemfile` and run bundler updates.
4. Update configuration files via `bin/rails app:update`.
5. Review framework defaults (`config.load_defaults` and `new_framework_defaults` initializer).
6. Handle framework-specific areas (Bootsnap, Active Storage, Action Cable, instrumentation) only when relevant to the app.

## 3) Per-version jump loop

For each version jump:

1. Read release notes for the target version.
2. Bump Rails and dependent framework gems.
3. Run bundle update for Rails stack.
4. Run `bin/rails app:update` and manually review generated diffs.
5. Boot the app and run smoke checks.
6. Resolve deprecations and failures before next jump.

Do not start the next version jump with unresolved deprecations or failing tests.

## 4) Config defaults strategy

- Keep existing defaults initially to reduce blast radius.
- Enable new defaults gradually and test after each change.
- Commit defaults toggles in small chunks so regressions are easy to isolate.

## 5) Mandatory verification gates

Run these after every significant upgrade step and at final completion:

```bash
bundle exec rspec
bundle exec rubocop
```

Completion criteria:

- `bundle exec rspec` exits with status 0.
- `bundle exec rubocop` exits with status 0.
- Both pass on the same commit/worktree state.

If either fails:

- Fix failures/offenses.
- Rerun both commands.
- Repeat until both are green.

## 6) Final handoff output

Provide:

- Final Rails and Ruby versions.
- Changed files summary (`Gemfile`, lockfile, config, initializers, environment files).
- Any intentional temporary compatibility settings still enabled.
- Follow-up items with priority (high/medium/low) and exact file paths.
