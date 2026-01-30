# Ruby Skills

A small collection of Codex skills focused on Ruby on Rails development.

Included skills:
- `ror-better-specs`: Rails/RSpec spec-writing guidance based on Better Specs.
- `ror-styleguide`: Rails style conventions based on rails.rubystyle.guide.

## Installation

1) Clone this repository.
2) Copy or symlink the skill folders into your Codex skills directory.

Example:

```sh
mkdir -p "$CODEX_HOME/skills"
cp -R betterspecs-skill "$CODEX_HOME/skills/"
cp -R ror-styleguide "$CODEX_HOME/skills/"
```

Notes:
- If `CODEX_HOME` is not set, the default is usually `~/.codex`.
- You can use symlinks instead of copying if you want live updates while editing.

## Usage

Mention a skill by name in your request (for example: “use ror-styleguide”) or ask a question that clearly matches its scope.

See `AGENTS.MD` for when each skill should be loaded.
