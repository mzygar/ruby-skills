# Routing

- Use member and collection routes for additional REST actions.
- Use the block syntax when declaring many member or collection routes.
- Use nested routes to express model relationships.
- Use shallow routes when nesting goes more than one level deep.
- Use namespaced routes to group related actions.
- Never use legacy wild controller routes.
- Avoid `match` unless mapping multiple verbs with `via:`.

## Examples

### Good

```ruby
# config/routes.rb
resources :subscriptions do
  member do
    get :unsubscribe
  end
end

resources :posts, shallow: true do
  resources :comments
end
```

### Bad

```ruby
# config/routes.rb
get 'subscriptions/:id/unsubscribe'
match ':controller(/:action(/:id(.:format)))'
```
