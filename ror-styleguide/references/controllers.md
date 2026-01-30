# Controllers

- Keep controllers skinny; move business logic to models or service objects.
- Keep controller actions small; after initial `find` or `new`, call only one method.
- Minimize instance variables shared between controller and view.
- Keep action filters scoped to the controller where they apply.

## Examples

### Good

```ruby
class OrdersController < ApplicationController
  def create
    order = OrderCreator.new(params).call
    redirect_to order
  end
end
```

### Bad

```ruby
class OrdersController < ApplicationController
  def create
    order = Order.new(order_params)
    order.total_cents = order.line_items.sum(&:subtotal_cents)
    order.apply_discounts
    order.save!
    notify_accounting(order)
    redirect_to order
  end
end
```
