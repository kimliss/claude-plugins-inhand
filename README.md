<div align="center">

# Claude Code Inhand

**Claude Code in hand, everything at your fingertips.**

A curated plugin marketplace for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) — 11 plugins across 6 categories, covering the full development lifecycle.

[![Plugins](https://img.shields.io/badge/plugins-11-blue)](plugins/)
[![Categories](https://img.shields.io/badge/categories-6-green)](#plugin-catalog)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](LICENSE)

[Getting Started](#getting-started) · [Plugin Catalog](#plugin-catalog) · [Contributing](#contributing)

</div>

---

## Features

- **Full-stack coverage** — Backend, frontend, mobile, DevOps, and database plugins
- **LSP integration** — Built-in language server support for Go, Java, Python, Vue, Swift, Dart
- **10 AI agents** — Planning, code review, TDD, security audit, architecture, and more
- **3 context modes** — Dev, research, and review workflows
- **Extensible** — Create your own plugins with the included template

## Getting Started

```bash
# Add the marketplace
claude plugin marketplace add kimliss/claude-code-inhand

# Install any plugin
claude plugin install dev-toolkit
claude plugin install go-dev
```

## Plugin Catalog

### Development

| Plugin | Description | LSP |
|--------|-------------|-----|
| [dev-toolkit](plugins/dev-toolkit/) | General-purpose toolkit with 10 agents, 3 context modes, 4 skills | — |

### Backend

| Plugin | Description | LSP |
|--------|-------------|-----|
| [go-dev](plugins/go-dev/) | Go development with project scaffolding | `gopls` |
| [java-dev](plugins/java-dev/) | Java / Spring Boot development | `jdtls` |
| [python-dev](plugins/python-dev/) | Python (Django / FastAPI) development | `Pyright` |

### Frontend

| Plugin | Description | LSP |
|--------|-------------|-----|
| [vue-dev](plugins/vue-dev/) | Vue.js / Nuxt development | `Vue Language Server` |
| [react-dev](plugins/react-dev/) | React / Next.js development | — |

### Mobile

| Plugin | Description | LSP |
|--------|-------------|-----|
| [android-dev](plugins/android-dev/) | Android / Kotlin / Jetpack Compose | — |
| [ios-dev](plugins/ios-dev/) | iOS / Swift / SwiftUI | `sourcekit-lsp` |
| [flutter-dev](plugins/flutter-dev/) | Flutter / Dart cross-platform | `Dart Language Server` |

### DevOps

| Plugin | Description | LSP |
|--------|-------------|-----|
| [devops-toolkit](plugins/devops-toolkit/) | CI/CD, Docker, Kubernetes, Terraform | — |

### Database

| Plugin | Description | LSP |
|--------|-------------|-----|
| [database-toolkit](plugins/database-toolkit/) | Schema design, query optimization, migrations | — |

## dev-toolkit

The core plugin that powers your daily workflow.

| Component | Details |
|-----------|---------|
| **Agents** | `planner` · `code-reviewer` · `tdd-guide` · `security-reviewer` · `architect` · `build-error-resolver` · `e2e-runner` · `refactor-cleaner` · `doc-updater` · `database-reviewer` |
| **Contexts** | `dev` — rapid implementation · `research` — exploration & learning · `review` — code quality & security |
| **Skills** | `iterative-retrieval` · `backend-patterns` · `frontend-patterns` · `explain-code` |

## Project Structure

```
claude-plugins-inhand/
├── .claude-plugin/
│   └── marketplace.json        # Plugin registry (11 plugins)
├── plugins/                    # All plugins
│   ├── dev-toolkit/
│   ├── go-dev/
│   ├── java-dev/
│   ├── python-dev/
│   ├── vue-dev/
│   ├── react-dev/
│   ├── android-dev/
│   ├── ios-dev/
│   ├── flutter-dev/
│   ├── devops-toolkit/
│   └── database-toolkit/
├── external_plugins/           # External plugin references (reserved)
└── templates/                  # Plugin development template
```

## Contributing

```bash
# Create a new plugin from template
cp -r templates/plugin-template plugins/your-plugin
```

See [CONTRIBUTING.md](templates/CONTRIBUTING.md) for the full guide.

## License

This project is licensed under the [GNU General Public License v3.0](LICENSE).
