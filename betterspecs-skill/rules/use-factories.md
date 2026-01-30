# Use factories and not fixtures

## Rules

- Prefer factories for clarity, flexibility, and explicit setup.
- Avoid fixtures when they obscure what the example needs.
- If using fixtures in unit tests, keep them small and easy to reason about.

## Bad example

```ruby
let(:user) { users(:bob) }
```

## Good example

```ruby
let(:user) { create(:user) }
```
