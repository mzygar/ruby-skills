# Active Support Core Extensions

- Prefer Ruby's safe navigation operator `&.` over `try!`.
- Prefer Ruby standard library methods over Active Support aliases.
- Prefer Ruby standard library over uncommon Active Support extensions.
- Prefer Ruby comparison operators over `Array#inquiry` and `String#inquiry`.
- Prefer `exclude?` over negated `include?`.
- Prefer squiggly heredoc (`<<~`) over `strip_heredoc` (Ruby 2.3+).
- Prefer `to_fs` over `to_formatted_s` (Rails 7.0+).

## Examples

### Good

```ruby
user&.profile
roles.exclude?('admin')
name = value.presence || 'Guest'
```

### Bad

```ruby
user.try!(:profile)
!roles.include?('admin')
```
