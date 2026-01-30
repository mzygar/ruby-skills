# Time

- Configure the application time zone in `application.rb`.
- Use `Time.zone.parse` instead of `Time.parse`.
- Avoid `String#to_time`; parse in the app time zone instead.
- Use `Time.zone.now` or `Time.current` instead of `Time.now`.
- Prefer `all_day`, `all_week`, `all_month`, `all_quarter`, and `all_year` over explicit range construction.

## Examples

### Good

```ruby
Time.zone.parse('2024-01-15 09:30')
Time.current
Date.current
User.where(created_at: Date.current.all_day)
```

### Bad

```ruby
Time.parse('2024-01-15 09:30')
Time.now
Date.today
User.where(created_at: Date.current.beginning_of_day..Date.current.end_of_day)
```
