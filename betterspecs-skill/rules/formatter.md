# Useful formatter

## Rules

- Use a readable formatter such as Fuubar for progress output.
- Configure RSpec to use the formatter in `.rspec` or `spec_helper`.
- Keep output concise while still showing failures clearly.

## Bad example

```text
# No formatter configured.
```

## Good example

```text
# .rspec
--format Fuubar
```
