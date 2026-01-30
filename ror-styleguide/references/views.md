# Views

- Never call the model layer directly from a view.
- Avoid complex formatting in views; use helpers, decorators, or presenters.
- Use partials to reduce duplication.
- Avoid instance variables in partials; pass locals to `render` instead.

## Examples

### Good

```erb
<%= render partial: 'user', locals: { user: user } %>
```

### Bad

```erb
<%# app/views/users/index.html.erb %>
<% User.where(active: true).each do |user| %>
  <%= user.email %>
<% end %>
```
