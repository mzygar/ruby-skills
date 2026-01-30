# Test all possible cases

## Rules

- Cover the valid case, edge cases, and invalid cases.
- Use contexts to show each case clearly.
- Prioritize behavior and outcomes over internal implementation.

## Bad example

```ruby
describe '#discount' do
  it 'applies a discount' do
    # ...
  end
end
```

## Good example

```ruby
describe '#discount' do
  context 'when the user is a member' do
    it 'applies a discount' do
      # ...
    end
  end

  context 'when the user is not a member' do
    it 'does not apply a discount' do
      # ...
    end
  end
end
```
