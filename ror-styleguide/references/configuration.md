# Configuration

- Put custom initialization code in `config/initializers`.
- Keep per-gem initialization in a separate initializer named after the gem.
- Keep environment-specific settings in `config/environments/*` and precompile extra assets there as needed.
- Keep shared configuration in `config/application.rb`.
- Align `config.load_defaults` with the Rails version when upgrading.
- Avoid extra environment files; prefer env vars for staging-like config.
- Keep extra configuration in YAML under `config/` and load it with `config_for`.

## Examples

### Good

```ruby
# config/initializers/sidekiq.rb
Sidekiq.configure_server do |config|
  config.redis = { url: ENV.fetch('REDIS_URL') }
end

# config/application.rb
config.x.billing.provider = 'stripe'

# config/environments/production.rb
config.assets.precompile += %w[admin.css admin.js]

# config/settings.yml
billing:
  retries: 3
```

### Bad

```ruby
# config/initializers/app_config.rb
# Global app config and load defaults misplaced in an initializer
config.load_defaults 7.0
config.x.billing.provider = 'stripe'

# config/environments/staging.rb
# Custom environment file added instead of using env vars
```
