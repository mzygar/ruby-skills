# Use subject

## Rules

- Use `subject` to express the object under test.
- Use a named `subject(:name)` when it improves readability.
- Avoid referencing `subject` explicitly in examples if implicit use is clearer.

## Bad example

```ruby
describe User do
  before { @user = build(:user) }

  it 'is valid' do
    expect(@user).to be_valid
  end
end
```

## Good example

```ruby
describe User do
  subject(:user) { build(:user) }

  it 'is valid' do
    expect(user).to be_valid
  end
end
```
