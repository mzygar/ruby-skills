# Mock or not to mock

## Rules

- Avoid mocking unless you have a clear need to isolate external boundaries.
- Use real objects in unit tests when they are fast and deterministic.
- If mocking, keep expectations minimal and focused on behavior.

## Bad example

```ruby
it 'creates a user' do
  user = instance_double(User)
  expect(User).to receive(:new).and_return(user)
  expect(user).to receive(:save!).and_return(true)
  expect(subject.create_user).to eq(true)
end
```

## Good example

```ruby
it 'creates a user' do
  user = subject.create_user
  expect(user).to be_persisted
end
```
