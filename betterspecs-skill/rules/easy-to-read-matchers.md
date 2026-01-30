# Easy to read matchers

## Rules

- Use matchers that read like plain English.
- Prefer higher-level matchers (e.g., `be_valid`, `have_attribute`, `change`).
- Avoid complex custom logic inside expectations when a matcher exists.

## Bad example

```ruby
lambda { user.save! }.should raise_error(ActiveRecord::RecordInvalid)
```

## Good example

```ruby
expect { user.save! }.to raise_error(ActiveRecord::RecordInvalid)
```
