# Testing

- Prefer integration style controller tests over functional style controller tests.
- Prefer `freeze_time` over `travel_to` when you want to freeze the current time.

## Examples

### Good

```ruby
class OrdersTest < ActionDispatch::IntegrationTest
  include ActiveSupport::Testing::TimeHelpers

  test 'freezes time when calculating totals' do
    freeze_time do
      post orders_path, params: { order: { total_cents: 1000 } }
    end
  end
end
```

### Bad

```ruby
travel_to(Time.current) do
  post orders_path, params: { order: { total_cents: 1000 } }
end
```
