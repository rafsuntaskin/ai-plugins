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

Then install a listed plugin by name:

```bash
codex plugin add stackshot
```

## Plugins

| Plugin | Description | Category | Direct install |
|--------|-------------|----------|----------------|
| [claude-usage-in-status](https://github.com/rafsuntaskin/claude-usage-in-status) | Live token usage and rate limit status in your statusline after every prompt | productivity | `claude plugin add github:rafsuntaskin/claude-usage-in-status` |
| [stackshot](https://github.com/rafsuntaskin/stackshot) | Generate repository tech stack card image prompts from project metadata, LOC, tests, tools, and styling signals | productivity | `codex plugin add github:rafsuntaskin/stackshot` |

## Direct GitHub Install

If you do not want to use the marketplace, install a plugin directly from its GitHub repo.

For Codex:

```bash
codex plugin add github:rafsuntaskin/stackshot
```

For Claude Code:

```bash
claude plugin add github:rafsuntaskin/claude-usage-in-status
```

## Local Development

Clone a plugin repo, then install from the local path:

```bash
git clone https://github.com/rafsuntaskin/stackshot.git
codex plugin add ./stackshot
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
