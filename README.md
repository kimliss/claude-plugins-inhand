# Claude Plugins Inhand

Claude Code Plugin Marketplace - 按开发场景分类组织的插件集合。

## Quick Start

```bash
# 添加 marketplace
claude plugin marketplace add /path/to/claude-plugins-inhand

# 安装插件
claude plugin install dev-toolkit
claude plugin install go-dev
```

## Plugin Catalog

### Development

| Plugin | Description | LSP |
|--------|-------------|-----|
| [dev-toolkit](plugins/dev-toolkit/) | 通用开发工具：10 个 agents、3 种上下文模式、4 个 skills | - |

### Backend

| Plugin | Description | LSP |
|--------|-------------|-----|
| [go-dev](plugins/go-dev/) | Go 开发，项目脚手架 | gopls |
| [java-dev](plugins/java-dev/) | Java/Spring Boot 开发 | jdtls |
| [python-dev](plugins/python-dev/) | Python (Django/FastAPI) 开发 | Pyright |

### Frontend

| Plugin | Description | LSP |
|--------|-------------|-----|
| [vue-dev](plugins/vue-dev/) | Vue.js/Nuxt 开发 | Vue Language Server |
| [react-dev](plugins/react-dev/) | React/Next.js 开发 | - |

### Mobile

| Plugin | Description | LSP |
|--------|-------------|-----|
| [android-dev](plugins/android-dev/) | Android/Kotlin/Jetpack Compose | - |
| [ios-dev](plugins/ios-dev/) | iOS/Swift/SwiftUI | sourcekit-lsp |
| [flutter-dev](plugins/flutter-dev/) | Flutter/Dart 跨平台 | Dart Language Server |

### DevOps

| Plugin | Description | LSP |
|--------|-------------|-----|
| [devops-toolkit](plugins/devops-toolkit/) | CI/CD, Docker, Kubernetes, Terraform | - |

### Database

| Plugin | Description | LSP |
|--------|-------------|-----|
| [database-toolkit](plugins/database-toolkit/) | Schema 设计, 查询优化, Migration | - |

## dev-toolkit Highlights

核心插件，提供：

**10 Agents**: planner, code-reviewer, tdd-guide, security-reviewer, architect, build-error-resolver, e2e-runner, refactor-cleaner, doc-updater, database-reviewer

**3 Contexts**: dev (快速开发), research (探索调研), review (代码审查)

**4 Skills**: iterative-retrieval, backend-patterns, frontend-patterns, explain-code

## Create Your Own Plugin

```bash
cp -r templates/plugin-template plugins/your-plugin
```

See [CONTRIBUTING.md](templates/CONTRIBUTING.md) for details.

## Project Structure

```
claude-plugins-inhand/
├── .claude-plugin/marketplace.json   # Plugin registry (11 plugins)
├── plugins/                          # All plugins
├── external_plugins/                 # External plugin references (reserved)
└── templates/                        # Plugin development template
```

## License

See [LICENSE](LICENSE).
