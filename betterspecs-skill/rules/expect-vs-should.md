# Expect vs should syntax

## Rules

- Prefer the `expect` syntax (`expect(x).to ...`).
- Use one-liners with `is_expected` or `are_expected` when it improves clarity.
- Avoid the old `should` syntax in new specs.

## Bad example

```ruby
it 'is valid' do
  user.should be_valid
end
```

## Good example

```ruby
it 'is valid' do
  expect(user).to be_valid
end

it { is_expected.to be_valid }
```
