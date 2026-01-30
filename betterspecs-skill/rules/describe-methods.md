# Describe your methods

## Rules

- Use `.` to describe class methods and `#` to describe instance methods.
- Use the actual method name in `describe` instead of a vague sentence.
- Use `::` for constants and modules when it makes the target clearer.

## Bad example

```ruby
describe 'the authenticate method for User' do
  describe 'if the user is an admin' do
    # ...
  end
end
```

## Good example

```ruby
describe '.authenticate' do
  # class method
end

describe '#admin?' do
  # instance method
end
```
