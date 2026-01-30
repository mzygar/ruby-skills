# Managing Processes

- Use Foreman to manage app processes in development.

## Examples

### Good

```
# Procfile
web: bin/rails server
worker: bundle exec sidekiq
```

```
foreman start
```

### Bad

```
# Start each process manually in separate terminals with ad-hoc commands
```
