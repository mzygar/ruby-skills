# Models

- Introduce non-Active Record model classes freely when they improve design.
- Choose meaningful model names and avoid abbreviations.
- Use `ActiveModel::Model` (and `ActiveModel::Attributes` if needed) when you want model-like behavior without a database table.
- Keep formatting or presentation logic out of models; use helpers, presenters, or decorators.

## Examples

### Good

```ruby
# app/models/signup_form.rb
class SignupForm
  include ActiveModel::Model
  attr_accessor :email, :terms_accepted
end

# app/presenters/user_presenter.rb
class UserPresenter
  def initialize(user)
    @user = user
  end

  def display_name
    "#{@user.first_name} #{@user.last_name}"
  end
end
```

### Bad

```ruby
class User < ApplicationRecord
  def display_name
    "#{first_name} #{last_name}".titleize
  end
end
```
