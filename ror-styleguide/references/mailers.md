# Mailers

- Name mailers with the `SomethingMailer` suffix.
- Provide both HTML and plain-text view templates.
- Enable delivery errors in development.
- Use a local SMTP server in development.
- Set default hostnames for URLs in mailers.
- Format email addresses as `"Name <email@example.com>"`.
- Set test delivery method to `:test`.
- Use SMTP delivery for development and production.
- Inline styles in HTML emails; use a gem to inline styles if needed.
- Send email in background jobs instead of during request processing.

## Examples

### Good

```ruby
class UserMailer < ApplicationMailer
  def welcome(user)
    @user = user
    mail(to: @user.email, subject: 'Welcome')
  end
end

UserMailer.welcome(user).deliver_later
```

### Bad

```ruby
class Mailer < ApplicationMailer
  def welcome(user)
    mail(to: user.email, body: "<h1>Welcome</h1>")
  end
end

UserMailer.welcome(user).deliver_now
```
