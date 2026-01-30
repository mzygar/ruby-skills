---
name: ror-styleguide
description: Ruby on Rails style guide rules and review checklist based on rails.rubystyle.guide. Use when asked to apply, summarize, or enforce Rails style conventions for configuration, routing, controllers, models, migrations, views, i18n, assets, mailers, Active Support, time/duration, bundler, testing, or process management.
---

# Rails Style Guide

## Workflow

- Identify the Rails area(s) in scope (for example: routing, controllers, models, migrations, views, i18n, assets, mailers, Active Support, time/duration, bundler, testing, processes).
- Load the matching section file(s) from `references/` before responding.
- If the request spans multiple areas, read each relevant file and reconcile overlaps; prefer the most specific section.
- Call out version-specific guidance explicitly (for example, Rails 6.1+ or Rails 7.0+).
- If the guide does not cover a rule, say so and suggest checking the official guide section instead of inventing guidance.
- Keep responses anchored to the guide’s intent; do not introduce new conventions unless asked.

## How to respond

- Prefer concise, actionable guidance with direct mapping to the section rules.
- When reviewing code, list concrete findings, each with:
  - the violated rule,
  - the reason (why it matters),
  - a corrected example.
- Use the Good/Bad examples in each section file as templates for your response.
- If code is ambiguous, ask one clarifying question rather than guessing (for example: Rails version, app structure, or preferred test framework).
- Avoid long quotations from the guide; summarize in your own words and point to the section file.

## Section files (when to use each)

- `references/introduction.md` - guide context, scope, and how it relates to the Ruby style guide
- `references/configuration.md` - app and environment configuration, initializers, config files
- `references/routing.md` - routes.rb structure, RESTful routing, nesting, and namespaces
- `references/controllers.md` - controller responsibilities, action size, and shared state
- `references/controllers-rendering.md` - render/response conventions and status usage
- `references/models.md` - non-AR models, naming, and presentation boundaries
- `references/models-active-record.md` - AR macros, validations, callbacks, associations, and persistence
- `references/models-active-record-queries.md` - query style, where/order/find, and SQL safety
- `references/migrations.md` - migration structure, constraints, reversibility, and data changes
- `references/views.md` - view logic boundaries, partials, and locals usage
- `references/internationalization.md` - i18n keys, locale files, and translation patterns
- `references/assets.md` - asset pipeline placement and third-party assets
- `references/mailers.md` - mailer naming, delivery configuration, and email templates
- `references/active-support-core-extensions.md` - preferred core extensions and Ruby alternatives
- `references/time.md` - time zone usage, parsing, and time helpers
- `references/duration.md` - duration helpers and time arithmetic patterns
- `references/bundler.md` - Gemfile grouping and dependency hygiene
- `references/testing.md` - testing style preferences and time helpers
- `references/managing-processes.md` - process management in development
- `references/further-reading.md` - recommended books and docs for deeper guidance
- `references/contributing.md` - contribution workflow for the guide itself
- `references/license.md` - licensing and attribution requirements
- `references/spread-the-word.md` - sharing and attribution guidance
