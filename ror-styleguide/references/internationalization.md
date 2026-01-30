# Internationalization

- Move locale-specific strings and settings to locale files under `config/locales`.
- Use the `activerecord` scope for translated model and attribute labels.
- Separate model translations and view texts (for example, `locales/models` and `locales/views`).
- Put shared localization (date, currency formats) at the root of the locales directory.
- Prefer short I18n method forms (`I18n.t`, `I18n.l`).
- Use lazy lookup in views and controllers when it improves readability.
- Use dot-separated keys instead of `:scope` arrays or symbols.
- Consult the Rails I18n guides for details.

## Examples

### Good

```erb
<h1><%= t('.title') %></h1>
```

```yml
# config/locales/views/users/en.yml
en:
  users:
    index:
      title: "Users"
```

### Bad

```erb
<h1>Users</h1>
```
