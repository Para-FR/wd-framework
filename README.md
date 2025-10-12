# WD Framework (Web Development) v2.0

⚡ Intelligent web development framework with **22 specialized commands**, **5 expert agents**, **11 AI personas**, and complete orchestration system for Claude Code.

## 🚀 Installation

```bash
/plugin marketplace add Para-FR/wd-framework
```

Then restart Claude Code to activate the framework.

## ✨ What's New in v2.0

### Intelligent Orchestration System
- **Auto-Routing**: Automatically detects intent and routes to optimal agents
- **Wave Orchestration**: Multi-stage execution for complex tasks (30-50% better results)
- **11 AI Personas**: Specialized behaviors for different domains
- **Smart MCP Coordination**: Context7, Sequential, Magic, Playwright
- **Quality Gates**: 8-step validation cycle for production-ready code

[📖 Read Full Orchestration Guide →](ORCHESTRATION.md)

## 📦 Commands (22)

### Core Commands
- `/wd:analyze` - Multi-dimensional code analysis
- `/wd:implement` - Feature implementation with auto-persona
- `/wd:build` - Project builder with framework detection
- `/wd:improve` - Code quality improvements
- `/wd:test` - Testing and QA workflows
- `/wd:document` - Documentation generation
- `/wd:troubleshoot` - Issue diagnosis and resolution

### Quality & Enhancement
- `/wd:review` - Comprehensive code review (NEW)
- `/wd:benchmark` - Performance testing (NEW)
- `/wd:cleanup` - Code cleanup
- `/wd:finalize` - Project finalization (NEW)

### Planning & Design
- `/wd:design` - System design
- `/wd:brainstorm` - Structured idea generation (NEW)
- `/wd:estimate` - Development estimation
- `/wd:workflow` - Workflow generation

### Migration & Transformation
- `/wd:migrate` - Framework migration assistant (NEW)

### Utilities
- `/wd:explain` - Code explanation
- `/wd:git` - Git operations with smart commits
- `/wd:index` - Project indexing
- `/wd:load` - Context loading
- `/wd:spawn` - Task orchestration
- `/wd:task` - Long-term task management

## 🤖 Agents (5)

Specialized sub-agents using Claude Code's native Task tool:

- **wd-frontend-agent** - UI/UX, React, Vue, accessibility
- **wd-backend-agent** - APIs, databases, microservices
- **wd-security-agent** - Vulnerability assessment, compliance
- **wd-test-agent** - E2E testing, quality assurance
- **wd-docs-agent** - Documentation, knowledge management

## 🧠 AI Personas (11)

Auto-activating specialized behaviors:

- `--persona-architect` - Systems design
- `--persona-frontend` - UI/UX specialist
- `--persona-backend` - Reliability engineer
- `--persona-security` - Threat modeling
- `--persona-performance` - Optimization
- `--persona-analyzer` - Root cause analysis
- `--persona-qa` - Quality assurance
- `--persona-refactorer` - Code quality
- `--persona-devops` - Infrastructure
- `--persona-mentor` - Knowledge transfer
- `--persona-scribe` - Documentation

## 🔧 MCP Server Integration

Smart coordination of 4 MCP servers:
- **Context7**: Library docs, best practices
- **Sequential**: Complex analysis, debugging
- **Magic**: UI component generation
- **Playwright**: Browser automation, E2E testing

## 🎯 Usage Examples

### Auto-Activation (Recommended)
```bash
# Automatically activates frontend persona + Magic MCP
/wd:implement LoginComponent

# Automatically activates security persona + Sequential MCP
/wd:review auth-system --focus security
```

### Multi-Agent Coordination
```bash
# Parallel agents for comprehensive review
/wd:review --comprehensive --agents security,performance,quality

# Full-stack feature with agent pipeline
/wd:implement user-dashboard --agents frontend,backend,test,docs
```

### Wave Orchestration
```bash
# Multi-stage complex refactoring
/wd:improve legacy-code --wave-mode force --wave-strategy systematic
```

## 📚 Documentation

- **[ORCHESTRATION.md](ORCHESTRATION.md)** - Complete orchestration guide
- **`.claude/ORCHESTRATOR.md`** - Routing intelligence details
- **`.claude/PERSONAS.md`** - AI personas reference
- **`.claude/AGENTS.md`** - Agent system documentation
- **`.claude/FLAGS.md`** - Flag system reference
- **`.claude/MCP.md`** - MCP server coordination

## 🛠️ Technologies

React, Next.js, Vue, Angular, TypeScript, Tailwind CSS, Node.js, Python, and more...

## 📄 License

MIT © Para CC-France
