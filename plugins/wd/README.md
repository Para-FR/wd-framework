# WD Framework v2.3.0

⚡ Intelligent web development framework with **22 commands** | **5 agents** | **11 personas** | **4 MCP servers**

Inspired by [BMAD-METHOD](https://github.com/bmad-code-org/BMAD-METHOD) patterns for AI-assisted development.

## 🚀 Installation

```bash
/plugin marketplace add Para-FR/wd-framework
```

## ✨ What's New in v2.3

### BMAD-METHOD Integration
- **Progressive Disclosure** - Step-by-step workflows, no skipping
- **Story File Authority** - Single source of truth for task execution
- **ADR Pattern** - Architecture Decision Records for multi-agent consistency
- **Development Tracks** - Quick/Standard/Enterprise workflow selection
- **Skill Level Adaptation** - Beginner/Intermediate/Expert output modes
- **YOLO Mode** - Automated execution with minimal checkpoints
- **Facilitation Mode** - Guided discovery over direct generation
- **Document Sharding** - ~90% token reduction for large codebases

### Core Files (7)
| File | Purpose | Size |
|------|---------|------|
| CLAUDE.md | Entry point | 1 KB |
| CORE.md | Principles + Rules | 3 KB |
| ROUTING.md | Orchestration + Wave + ADR + Tracks | 6 KB |
| CAPABILITIES.md | Personas + Agents + MCP + Facilitation | 6.8 KB |
| COMMANDS.md | Command reference | 4.9 KB |
| FLAGS.md | Flag reference + Skill/Track/YOLO | 6.3 KB |
| WORKFLOWS.md | Story File + Sharding + Adversarial Review | 2.8 KB |

## 📦 Commands (22)

### Development
`/wd:build` | `/wd:implement` | `/wd:migrate` | `/wd:design`

### Analysis
`/wd:analyze` | `/wd:troubleshoot` | `/wd:explain`

### Quality
`/wd:improve` | `/wd:cleanup` | `/wd:review`

### Testing
`/wd:test` | `/wd:benchmark`

### Planning
`/wd:brainstorm` | `/wd:estimate` | `/wd:workflow`

### Workflow
`/wd:finalize` | `/wd:git` | `/wd:document`

### Meta
`/wd:index` | `/wd:load` | `/wd:spawn` | `/wd:task`

## 🤖 Agents (5)

| Agent | Domain | Primary MCP |
|-------|--------|-------------|
| wd-frontend-agent | UI/UX, React, Vue | Magic |
| wd-backend-agent | APIs, databases | Context7 |
| wd-security-agent | Vulnerability, compliance | Sequential |
| wd-test-agent | E2E, QA | Playwright |
| wd-docs-agent | Documentation | Context7 |

## 🧠 Personas (11)

| Persona | Focus | Auto-Triggers |
|---------|-------|---------------|
| architect | Systems design | architecture, scalability |
| frontend | UI/UX, a11y | component, responsive |
| backend | Reliability, APIs | API, database, server |
| security | Threat modeling | vulnerability, auth |
| performance | Optimization | bottleneck, optimize |
| analyzer | Root cause | analyze, investigate |
| qa | Testing | test, quality |
| refactorer | Code quality | refactor, cleanup |
| devops | Infrastructure | deploy, CI/CD |
| mentor | Knowledge transfer | explain, learn |
| scribe | Documentation | document, write |

## 🔧 MCP Integration

| Server | Purpose | Flag |
|--------|---------|------|
| Context7 | Library docs, patterns | `--c7` |
| Sequential | Complex analysis | `--seq` |
| Magic | UI components | `--magic` |
| Playwright | E2E testing | `--play` |

## 🎯 Quick Examples

```bash
# Auto-activates frontend persona + Magic
/wd:implement LoginComponent

# Security review with agent
/wd:review auth-system --focus security

# Multi-agent coordination
/wd:review --agents security,performance,quality

# Wave orchestration for complex tasks
/wd:improve legacy-code --wave-mode force
```

## 🆕 New Flags (v2.3)

```bash
# Skill Level
--skill-level beginner|intermediate|expert

# Development Tracks
--track quick|standard|enterprise

# Execution Modes
--yolo                  # Automated execution
--facilitation          # Guided discovery mode

# Document Sharding
--sharding auto|full|selective|index

# Output Formats
--output story|adr      # Generate story files or ADRs
```

## ⚡ Key Features

- **Auto-Routing**: Intent detection → optimal agent/persona
- **Wave Orchestration**: Multi-stage execution (complexity ≥0.7)
- **Quality Gates**: 8-step validation cycle
- **Smart Delegation**: Auto-delegate on >50 files or >7 dirs
- **BMAD Protocol**: Story files, ADRs, progressive disclosure

## 📚 Documentation

- [ORCHESTRATION.md](docs/ORCHESTRATION.md) - Complete guide
- [PLUGIN_DEVELOPMENT.md](docs/PLUGIN_DEVELOPMENT.md) - Dev guide

## 📄 License

MIT © Para CC-France
