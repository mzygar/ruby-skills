# Models: Active Record

- Avoid changing Active Record defaults (table names, primary keys, foreign keys) unless required.
- Append to `ignored_columns` instead of resetting it.
- Define `enum` values using hash syntax to make them explicit.
- Group macro-style methods at the top of the class in a consistent order (scopes, constants, attrs, validations, callbacks, associations, etc.).
- Prefer `has_many :through` over `has_and_belongs_to_many`.
- Use `self[:attribute]` for read and write instead of `read_attribute`/`write_attribute`.
- Use the new-style validation syntax (`validates ...`) whenever possible.
- Name custom validation methods to read naturally with `validate` (for example, `validate :expiration_date_cannot_be_in_the_past`).
- Use a single-attribute validation per `validates` call.
- Create custom validator classes for reusable or complex validations.
- Keep custom validators under `app/validators`.
- Extract shared validators to a separate gem when reused across apps.
- Use named scopes freely.
- For complex parameterized scopes, use a class method that returns an `ActiveRecord::Relation`.
- Order callbacks in the order they will run.
- Be cautious with methods that skip validations; prefer methods that run validations.
- Provide user-friendly URLs via `to_param` or `friendly_id`.
- Use `find_each` for batch processing.
- For dependent associations that need validation, use `before_destroy` with `prepend: true`.
- Always specify a `dependent` option on `has_many` and `has_one`.
- Use bang persistence methods or handle return values explicitly (`save`, `create`, `update`, `destroy`).

## Examples

### Good

```ruby
class Article < ApplicationRecord
  enum status: { draft: 0, published: 1 }

  has_many :taggings, dependent: :destroy
  has_many :tags, through: :taggings

  validates :title, presence: true

  before_destroy :ensure_no_comments, prepend: true

  def ensure_no_comments
    throw(:abort) if comments.exists?
  end
end
```

### Bad

```ruby
class Article < ApplicationRecord
  enum status: [:draft, :published]
  has_and_belongs_to_many :tags

  validate :title_present
  def title_present
    errors.add(:title, "can't be blank") if title.blank?
  end
end
```
