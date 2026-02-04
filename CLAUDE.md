# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Claude Code Plugin Marketplace，按开发场景分类组织的插件集合。包含 11 个插件，覆盖通用开发、后端、前端、移动端、DevOps 和数据库场景。

## Repository Structure

```
claude-plugins-inhand/
├── .claude-plugin/
│   └── marketplace.json              # 核心索引（注册所有 11 个插件）
│
├── plugins/                          # 所有内嵌插件
│   ├── dev-toolkit/                  # 通用开发工具（agents, contexts, skills, hooks）
│   ├── go-dev/                       # Go 开发（gopls LSP）
│   ├── java-dev/                     # Java/Spring（jdtls LSP）
│   ├── python-dev/                   # Python（Pyright LSP）
│   ├── vue-dev/                      # Vue.js（Vue Language Server）
│   ├── react-dev/                    # React/Next.js
│   ├── android-dev/                  # Android/Kotlin
│   ├── ios-dev/                      # iOS/Swift（sourcekit-lsp）
│   ├── flutter-dev/                  # Flutter/Dart（Dart Language Server）
│   ├── devops-toolkit/               # DevOps（CI/CD, Docker, K8s）
│   └── database-toolkit/            # 数据库（SQL, Schema, Migration）
│
├── external_plugins/                 # 外部插件引用（预留）
│
├── templates/                        # 新插件开发模板
│   ├── plugin-template/              # 插件骨架模板
│   └── CONTRIBUTING.md               # 贡献指南
│
└── .claude/
    └── settings.json                 # 本地插件启用配置
```

## Plugin Categories

| Category | Plugins | Description |
|----------|---------|-------------|
| development | dev-toolkit | 通用开发工具，10 个 agents，3 种上下文模式 |
| backend | go-dev, java-dev, python-dev | 后端语言/框架，含 LSP 支持 |
| frontend | vue-dev, react-dev | 前端框架 |
| mobile | android-dev, ios-dev, flutter-dev | 移动端开发 |
| devops | devops-toolkit | CI/CD, 容器, 基础设施 |
| database | database-toolkit | 数据库设计和优化 |

## dev-toolkit (Core Plugin)

### Agent System

| Agent | 使用时机 |
|-------|---------|
| planner | 复杂功能、重构前的规划 |
| code-reviewer | 代码编写后立即使用 |
| tdd-guide | 新功能、bug修复 |
| security-reviewer | 提交前安全检查 |
| architect | 架构决策 |
| build-error-resolver | 构建失败时 |
| e2e-runner | 端到端测试 |
| refactor-cleaner | 代码重构清理 |
| doc-updater | 文档更新 |
| database-reviewer | 数据库审查 |

### Development Contexts

- **dev.md**: 快速实现，先让代码工作
- **research.md**: 探索调研，学习优先
- **review.md**: 代码质量和安全审查

### Skills

- iterative-retrieval: 多 agent 工作流上下文优化
- backend-patterns: 后端设计模式
- frontend-patterns: 前端设计模式
- explain-code: 代码解释

## Code Standards

### Immutability (CRITICAL)
始终创建新对象，禁止变更：
```javascript
// 正确: 不可变
function updateUser(user, name) {
  return { ...user, name }
}
```

### File Organization
- 200-400行典型，最大800行
- 函数最大50行
- 嵌套深度最大4层

### Testing
- 最低覆盖率: 80%
- TDD流程: RED → GREEN → IMPROVE
- 测试类型: Unit + Integration + E2E

### Security Checks
提交前必查：
- 无硬编码密钥
- 输入验证
- SQL注入防护
- XSS防护

## Adding New Plugins

1. 复制 `templates/plugin-template/` 到 `plugins/your-plugin/`
2. 编辑 `plugin.json` 填写元数据
3. 在 `.claude-plugin/marketplace.json` 注册
4. 详见 `templates/CONTRIBUTING.md`

## Commit Format

```
<type>: <description>
```
Types: feat, fix, refactor, docs, test, chore, perf, ci
