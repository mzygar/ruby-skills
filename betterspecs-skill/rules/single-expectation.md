# Single expectation test

## Rules

- Prefer one expectation per example for clarity and fast feedback.
- Split multiple behaviors into separate examples.
- Allow multiple expectations in slower, higher-level integration specs where setup dominates.

## Bad example

```ruby
it 'validates fields' do
  expect(user).to be_valid
  expect(user.name).to eq('Ada')
  expect(user.email).to include('@')
end
```

## Good example

```ruby
it 'is valid' do
  expect(user).to be_valid
end

it 'has a name' do
  expect(user.name).to eq('Ada')
end
```
