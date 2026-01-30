# Models: Active Record Queries

- Avoid interpolating variables into SQL strings.
- Prefer named placeholders when a query has multiple placeholders.
- Use `find` for primary key lookups that should raise on missing records.
- Use `find_by` for attribute lookups that can return `nil`.
- Use hash conditions for `where` and `where.not`.
- Use `where.missing` to find records missing associations (Rails 6.1+).
- Do not order by `id`; order by an explicit timestamp column instead.
- Use symbol arguments for `order`.
- Use `pluck` for a single column across many records.
- Use `pick` for a single column on one record.
- Use `ids` to return an array of ids.
- Use squished heredocs when writing explicit SQL.
- Prefer `size` (or `length` when you need to load) over `count` when the relation might already be loaded.
- Use range objects in `where` for date/time filtering.
- Avoid `where.not` with multiple attributes; write the SQL explicitly.
- Remove redundant `all` except where it changes behavior.
- Avoid memoizing `find_by` with `||=`; guard with `defined?` instead.

## Examples

### Good

```ruby
User.where(email: email)
User.where('created_at >= :from', from: 1.week.ago)
User.where.missing(:profile)

User.find(id)            # raises if missing
User.find_by(email: email)
```

### Bad

```ruby
User.where("email = '#{email}'")
User.where("created_at >= #{1.week.ago}")
User.find_by(id: id)     # uses find_by for primary key
```
