---
name: ror-better-specs
description: Rails/RSpec spec-writing style guide based on Better Specs. Use when writing, reviewing, refactoring, or teaching Ruby on Rails specs; when asked for Better Specs rules or checklists; or when turning Better Specs guidance into examples or feedback.
---

# Better Specs (Rails/RSpec)

Use this skill to apply Better Specs guidance to Rails spec writing and reviews.

## Workflow (use on every request)

1) Identify spec type and scope: model, request, feature/system, job, mailer, service, lib.  
2) Load only the rule files that match the question.  
3) Apply guidance in this order: structure → naming → setup → expectations → speed.  
4) Provide fixes as concrete edits or short examples (do/don’t).  
5) When refactoring, preserve intent and minimize setup bloat.

## Spec-type guidance (default expectations)

- **Model/unit specs**: prefer `describe '#method'` or `'.method'`, lean setup, single expectations.  
- **Request/feature specs**: allow multiple expectations per example if setup dominates.  
- **Controller specs**: keep minimal; prefer request/feature specs for behavior.

## Common pitfalls to catch

- Vague `describe` strings (e.g., “when user is admin”).  
- Long `it` descriptions that repeat context.  
- Heavy `before` blocks and instance variables instead of `let`.  
- Over-mocking internal collaborators.  
- Large factories/fixtures that hide intent.  
- Multiple unrelated expectations in a single example.

## Rule map (load as needed)

- `rules/what-is-better-specs.md` for scope, intent, and background.
- `rules/describe-methods.md` for naming methods in `describe`.
- `rules/use-contexts.md` for structuring contexts with when/with/without.
- `rules/short-description.md` for keeping descriptions short.
- `rules/single-expectation.md` for single-assertion guidance and exceptions.
- `rules/all-possible-cases.md` for valid/edge/invalid coverage.
- `rules/expect-vs-should.md` for `expect` syntax and `is_expected`.
- `rules/use-subject.md` for `subject` and named subjects.
- `rules/use-let-and-let-bang.md` for `let` vs `let!`.
- `rules/mock-or-not-to-mock.md` for mock usage boundaries.
- `rules/create-the-data-you-need.md` for minimal data setup.
- `rules/use-factories.md` for factories over fixtures and unit-test caveats.
- `rules/easy-to-read-matchers.md` for readable matchers.
- `rules/shared-examples.md` for DRYing duplicated specs.
- `rules/test-what-you-see.md` for integration emphasis and controller testing.
- `rules/do-not-use-should.md` for example phrasing and syntax.
- `rules/continuous-testing.md` for Guard-based workflow.
- `rules/faster-tests-preloading-rails.md` for preloading Rails with tradeoffs.
- `rules/stubbing-http-requests.md` for WebMock/VCR usage.
- `rules/formatter.md` for Fuubar and formatter setup.
- `rules/contributing.md` for contributing guidance.

## Review checklist (copy/paste friendly)

- `describe` names use `.`/`#` correctly and match the method/constant.  
- `context` phrases read as “when/with/without/if …”.  
- `it` descriptions are short and don’t repeat the context.  
- `expect` syntax used; no `should` in examples.  
- One expectation per unit example (exceptions allowed in request/feature).  
- `subject`/`let` used; avoid `before` + instance vars.  
- Minimal data; factories over fixtures.  
- Matchers are readable.  
- Mock only at boundaries.

## Output style (keep consistent)

- Lead with the most important fix.  
- Provide a bad vs good example when helpful.  
- Keep snippets short and runnable.  
