# Ruby Skills

A small collection of Codex skills focused on Ruby on Rails development.

Included skills:
- `ror-better-specs`: Rails/RSpec spec-writing guidance based on Better Specs.
- `ror-styleguide`: Rails style conventions based on rails.rubystyle.guide.

Sources:
- Better Specs: https://www.betterspecs.org/
- Rails Style Guide: https://rails.rubystyle.guide/

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

### GitHub Copilot in VS Code (custom instructions)

GitHub Copilot does not install Codex skills directly. To make this repo's
guidance available to Copilot Chat, add custom instructions in the workspace.

1) Open this repo in VS Code with GitHub Copilot Chat enabled.
2) Enable instruction files (setting:
   `github.copilot.chat.codeGeneration.useInstructionFiles`).
3) Create `.github/copilot-instructions.md` and reference these guides, for
   example:

```md
Use betterspecs-skill/SKILL.md when writing or reviewing RSpec specs.
Use ror-styleguide/SKILL.md when applying Rails style conventions.
```

4) (Optional) Add path-specific instructions under
   `.github/instructions/*.instructions.md` with `applyTo` to scope guidance.
5) If you use the Copilot coding agent, it can also read `AGENTS.md`
   (already in this repo). Feature support varies across Copilot surfaces.

## Usage

Mention a skill by name in your request (for example: “use ror-styleguide”) or ask a question that clearly matches its scope.

See `AGENTS.MD` for when each skill should be loaded.
