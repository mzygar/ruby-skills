# Faster tests (preloading Rails)

## Rules

- Use a preloader (e.g., Zeus, Spork, Spin) to reduce test startup time.
- Evaluate tradeoffs in complexity and stability before adopting.
- Keep preloader configuration documented and consistent across the team.

## Bad example

```text
# No preloader; each run boots Rails from scratch.
$ bundle exec rspec spec/models/user_spec.rb
```

## Good example

```text
# Use a preloader for faster startup.
$ zeus rspec spec/models/user_spec.rb
```
