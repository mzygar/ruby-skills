# Controllers: Rendering

- Prefer rendering templates over inline rendering.
- Use `render plain:` instead of `render text:`.
- Use HTTP status symbols (for example, `:bad_request`) instead of numeric codes.

## Examples

### Good

```ruby
# app/controllers/products_controller.rb
class ProductsController < ApplicationController
  def index
    render :index
  end
end

# app/views/products/index.html.erb
<%= render partial: 'product', collection: @products %>
```

```ruby
render plain: 'OK'
render status: :forbidden
```

### Bad

```ruby
class ProductsController < ApplicationController
  def index
    render inline: "<% products.each do |p| %><p><%= p.name %></p><% end %>", type: :erb
  end
end

render text: 'OK'
render status: 403
```
