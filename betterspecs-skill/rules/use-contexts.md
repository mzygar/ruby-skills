# Use contexts

## Rules

- Use `context` to express conditions like `when`, `with`, `without`, `if`.
- Keep `describe` for the unit under test and `context` for the state.
- Use consistent phrasing so specs read like sentences.

## Bad example

```ruby
describe '#activate' do
  it 'returns true when user is active' do
    # ...
  end

  it 'returns false when user is inactive' do
    # ...
  end
end
```

## Good example

```ruby
describe '#activate' do
  context 'when the user is active' do
    it 'returns true' do
      # ...
    end
  end

  context 'when the user is inactive' do
    it 'returns false' do
      # ...
    end
  end
end
```
