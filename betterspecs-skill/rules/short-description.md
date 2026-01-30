# Keep your description short

## Rules

- Keep `it` descriptions short and focused (roughly under 40 characters).
- Avoid repeating context details already stated in `describe` or `context`.
- Prefer direct, present-tense verbs.

## Bad example

```ruby
context 'when a user is inactive' do
  it 'does not allow the user to activate the account' do
    # ...
  end
end
```

## Good example

```ruby
context 'when a user is inactive' do
  it 'rejects activation' do
    # ...
  end
end
```
