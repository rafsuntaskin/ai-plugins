# ai-plugins

A curated marketplace registry for AI coding assistant plugins.

The marketplace manifest lives at:

```text
.claude-plugin/marketplace.json
```

## Add This Marketplace

### Claude Code

```bash
claude plugin marketplace add rafsuntaskin/ai-plugins
```

After adding the marketplace, install a listed plugin by name from Claude Code's plugin UI or plugin command flow.

### Codex

```bash
codex plugin marketplace add rafsuntaskin/ai-plugins
```

This registers the marketplace with Codex. In the current Codex CLI, `codex plugin` only supports marketplace management from the terminal (`marketplace add`, `marketplace upgrade`, and `marketplace remove`). It does not provide a `codex plugin add <plugin>` subcommand.

After adding the marketplace, use Codex's plugin UI or plugin selection flow when available. For StackShot, you can also install the skill directly with the fallback below.

## Plugins

| Plugin | Description | Category | Direct install |
|--------|-------------|----------|----------------|
| [claude-usage-in-status](https://github.com/rafsuntaskin/claude-usage-in-status) | Live token usage and rate limit status in your statusline after every prompt | productivity | `claude plugin add github:rafsuntaskin/claude-usage-in-status` |
| [stackshot](https://github.com/rafsuntaskin/stackshot) | Generate repository tech stack card image prompts from project metadata, LOC, tests, tools, and styling signals | productivity | Copy `STACKSHOT.md` into `~/.codex/skills/stackshot/SKILL.md` |

## Direct Install Fallbacks

If you do not want to use the marketplace, install a plugin directly from its GitHub repo when your assistant supports that command.

For StackShot in Codex, install the skill directly:

```bash
git clone https://github.com/rafsuntaskin/stackshot.git
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills/stackshot"
cp stackshot/STACKSHOT.md "${CODEX_HOME:-$HOME/.codex}/skills/stackshot/SKILL.md"
```

Start a new Codex session after copying the skill.

For Claude Code:

```bash
claude plugin add github:rafsuntaskin/claude-usage-in-status
```

## Local Development

Clone a plugin repo, then install from the local path:

```bash
git clone https://github.com/rafsuntaskin/stackshot.git
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills/stackshot"
cp stackshot/STACKSHOT.md "${CODEX_HOME:-$HOME/.codex}/skills/stackshot/SKILL.md"
```

For Claude Code plugins:

```bash
git clone https://github.com/rafsuntaskin/claude-usage-in-status.git
claude plugin add ./claude-usage-in-status
```

## Submit A Plugin

To add a plugin to this marketplace, open a pull request and add an entry to [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json):

```json
{
  "name": "your-plugin-name",
  "source": {
    "source": "github",
    "repo": "your-username/your-plugin-name"
  },
  "description": "What your plugin does.",
  "category": "productivity",
  "tags": ["tag1", "tag2"]
}
```
