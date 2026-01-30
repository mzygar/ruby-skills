# Migrations

- Bump the schema version in `db/schema.rb` or `db/structure.sql` after every migration.
- Use `db:schema:load` to initialize a new database, not `db:migrate`.
- Prefer the default values Rails generates for new migrations; do not override without need.
- Use 3-state booleans to avoid NULL issues (`default: true` or `default: false`).
- Define foreign key constraints explicitly.
- Prefer `change` over `up`/`down` when possible.
- When data migrations need model behavior, define a minimal model class inside the migration.
- Name foreign keys meaningfully rather than using obscure abbreviations.
- Use `reversible` when a migration needs custom behavior in each direction.

## Examples

### Good

```ruby
class AddActiveToUsers < ActiveRecord::Migration[7.0]
  def change
    add_column :users, :active, :boolean, default: false, null: false
    add_reference :orders, :user, foreign_key: true
  end
end
```

### Bad

```ruby
class AddActiveToUsers < ActiveRecord::Migration[7.0]
  def up
    add_column :users, :active, :boolean
  end

  def down
    remove_column :users, :active
  end
end
```
