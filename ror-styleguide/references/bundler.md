# Bundler

- Put development and test gems in the appropriate Gemfile groups.
- Use only established gems; review source for little-known gems.
- Keep `Gemfile.lock` under version control.

## Examples

### Good

```ruby
group :development, :test do
  gem 'rspec-rails'
end
```

### Bad

```ruby
gem 'rspec-rails'
```
