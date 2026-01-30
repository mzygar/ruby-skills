# Duration

- Use `from_now` and `ago` for time shifts without parameters.
- Use `since`, `after`, `until`, or `before` with a time parameter.
- Avoid using negative numbers with duration helpers.
- Use duration helpers (`1.day`, `2.weeks`, etc.) for date/time arithmetic.

## Examples

### Good

```ruby
2.weeks.from_now
3.days.ago
1.day.since(Time.current)
```

### Bad

```ruby
-1.day.from_now
Time.current - 3.days
```
