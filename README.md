# Direct

A custom [Claude Code output style](https://code.claude.com/docs/en/output-styles) for clear, simple, brief prose.

Direct starts with one rule: **default to the shortest complete answer.** It asks Claude to lead with the finding, use plain words, name specific things, and remove filler and repetition. When you ask for depth, it includes the relevant reasoning and details. Brevity fails when it leaves out depth you requested.

The style exists to make technical responses easier to read and act on. It preserves reasons needed to evaluate recommendations, statements of uncertainty, and complete error reports. The full instructions and a before-and-after example are in [direct.md](direct.md).

## Install

Clone this repository, then copy the style into your user output styles directory:

```sh
git clone https://github.com/theredspoon/claude-direct-output-style.git
mkdir -p ~/.claude/output-styles
cp claude-direct-output-style/direct.md ~/.claude/output-styles/direct.md
```

If Claude Code is already running, restart it to load the file. Then select the style:

```text
/output-style Direct
```

To use Direct by default across projects, add `"outputStyle": "Direct"` to your existing `~/.claude/settings.json`. Preserve any other settings:

```json
{
  "outputStyle": "Direct"
}
```

Project settings can override this user default. For installation in a single project, copy `direct.md` into that project's `.claude/output-styles/` directory instead.

These installation and selection options follow the [Claude Code output style documentation](https://code.claude.com/docs/en/output-styles#change-your-output-style). The file sets `keep-coding-instructions: true` to retain Claude Code's built-in software engineering instructions when using its full system prompt.

## Update

Pull the latest version, then copy the file again:

```sh
git -C claude-direct-output-style pull --ff-only
cp claude-direct-output-style/direct.md ~/.claude/output-styles/direct.md
```

Restart Claude Code to load the updated style.
