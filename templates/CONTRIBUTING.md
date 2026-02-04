# Contributing to Claude Plugins Inhand

## Plugin Development Guide

### Getting Started

1. Copy the plugin template:
   ```bash
   cp -r templates/plugin-template plugins/your-plugin-name
   ```

2. Rename template files:
   ```bash
   mv plugins/your-plugin-name/.claude-plugin/plugin.json.template \
      plugins/your-plugin-name/.claude-plugin/plugin.json
   mv plugins/your-plugin-name/hooks/hooks.json.template \
      plugins/your-plugin-name/hooks/hooks.json
   ```

3. Replace placeholders in `plugin.json`:
   - `{{PLUGIN_NAME}}` - your plugin name (e.g., `my-toolkit`)
   - `{{PLUGIN_DESCRIPTION}}` - brief description
   - `{{AUTHOR_NAME}}` - your name

### Naming Conventions

| Type | Convention | Example |
|------|-----------|---------|
| Language plugins | `{language}-dev` | `go-dev`, `python-dev` |
| Framework plugins | `{framework}-dev` | `vue-dev`, `react-dev` |
| Toolkit plugins | `{domain}-toolkit` | `devops-toolkit`, `database-toolkit` |

### Plugin Structure

```
your-plugin/
├── .claude-plugin/
│   └── plugin.json        # Required: plugin metadata
├── agents/                # AI agents for specialized tasks
│   └── *.md
├── skills/                # Reusable skill modules
│   └── */SKILL.md
├── rules/                 # Development rules and standards
│   └── *.md
├── hooks/                 # Tool execution hooks
│   └── hooks.json
├── commands/              # Custom commands
│   └── *.md
└── .lsp.json              # Optional: Language Server config
```

### Plugin Quality Requirements

- [ ] `plugin.json` with valid name, description, version, and author
- [ ] At least one of: agents, skills, rules, or hooks
- [ ] All markdown files use clear, concise language
- [ ] No hardcoded paths or secrets
- [ ] Tested with `claude plugin validate`

### LSP Configuration

If your plugin supports a language with an LSP server, add `.lsp.json`:

```json
{
  "language_id": {
    "command": "language-server-binary",
    "args": ["--stdio"],
    "extensionToLanguage": {
      ".ext": "language_id"
    }
  }
}
```

### Submission Process

1. Fork this repository
2. Create your plugin following the structure above
3. Register your plugin in `.claude-plugin/marketplace.json`:
   ```json
   {
     "name": "your-plugin",
     "source": "./plugins/your-plugin",
     "description": "Brief description.",
     "category": "backend|frontend|mobile|devops|database|development",
     "tags": ["relevant", "tags"]
   }
   ```
4. Submit a Pull Request with:
   - Clear description of the plugin's purpose
   - List of agents/skills/rules included
   - Any LSP dependencies noted

### Categories

| Category | Description |
|----------|------------|
| `development` | General-purpose development tools |
| `backend` | Backend languages and frameworks |
| `frontend` | Frontend frameworks and tools |
| `mobile` | Mobile development platforms |
| `devops` | CI/CD, containers, infrastructure |
| `database` | Database tools and patterns |

### Commit Format

```
<type>: <description>
```

Types: `feat`, `fix`, `refactor`, `docs`, `test`, `chore`, `perf`, `ci`
