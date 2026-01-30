# Assets

- Use the asset pipeline to organize static files.
- Reserve `app/assets` for custom stylesheets, javascripts, or images.
- Use `lib/assets` for libraries that do not fit the scope of the application.
- Put third-party code in `vendor/assets`.
- Prefer gemified versions of assets when possible.

## Examples

### Good

```
app/assets/stylesheets/admin.css
vendor/assets/javascripts/jquery.js
```

### Bad

```
app/assets/javascripts/jquery.js
```
