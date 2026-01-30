# Do not use should

## Rules

- Avoid using "should" in example descriptions.
- Use present-tense verbs that read like behavior statements.
- Keep descriptions short and explicit.

## Bad example

```ruby
it 'should not change the status' do
  # ...
end
```

## Good example

```ruby
it 'does not change the status' do
  # ...
end
```
