# ai-plugins

A curated marketplace of plugins for AI coding assistants.

## Add this marketplace to Claude

```bash
claude plugin marketplace add rafsuntaskin/ai-plugins
```

## Plugins

| Plugin | Description | Category |
|--------|-------------|----------|
| [claude-usage-in-status](https://github.com/rafsuntaskin/claude-usage-in-status) | Live token usage and rate limit status in your statusline after every prompt | productivity |
| [stackshot](https://github.com/rafsuntaskin/stackshot) | Generate repository tech stack card image prompts from project metadata, LOC, tests, tools, and styling signals | productivity |

---

## Adding a Plugin to Claude Code

### Install via MCP (recommended)

```bash
claude mcp add github:rafsuntaskin/<plugin-name>
```

Or install from a local path:

```bash
claude mcp add /path/to/plugin
```

### Manual install

1. Clone the plugin repo:
   ```bash
   git clone https://github.com/rafsuntaskin/<plugin-name>
   ```
2. Add it to your Claude Code settings:
   ```bash
   claude mcp add /path/to/<plugin-name>
   ```
3. Restart Claude Code.

---

## Adding a Plugin to Codex

### Install via npm (if published)

```bash
npm install -g @rafsuntaskin/<plugin-name>
codex plugin add @rafsuntaskin/<plugin-name>
```

### Install from GitHub

```bash
codex plugin add github:rafsuntaskin/<plugin-name>
```

### Manual install

1. Clone the plugin repo:
   ```bash
   git clone https://github.com/rafsuntaskin/<plugin-name>
   cd <plugin-name>
   npm install
   ```
2. Register it with Codex:
   ```bash
   codex plugin add .
   ```

---

## Submit a Plugin

To add your plugin to this marketplace, open a pull request and add an entry to [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json):

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
