# Use let and let!

## Rules

- Prefer `let` for lazily evaluated helpers.
- Use `let!` only when eager setup is required by the example.
- Avoid instance variables for test setup unless absolutely necessary.

## Bad example

```ruby
before do
  @user = create(:user)
  @account = create(:account, user: @user)
end
```

## Good example

```ruby
let(:user) { create(:user) }
let!(:account) { create(:account, user: user) }
```
