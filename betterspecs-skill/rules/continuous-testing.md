# Continuous testing

## Rules

- Use Guard (or similar) to run specs automatically on file changes.
- Start Guard with `bundle exec guard` during development.
- Keep the feedback loop tight by running only relevant specs.

## Bad example

```text
# Manually run the whole suite after each change.
$ bundle exec rspec
```

## Good example

```text
# Run Guard to re-run impacted specs.
$ bundle exec guard
```
