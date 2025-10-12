# WD Framework Orchestration System

## Overview

WD Framework v2.0 includes a complete intelligent orchestration system that automatically optimizes command execution, routes tasks to specialized agents, and coordinates MCP servers for maximum productivity.

## Core Components

### 1. Intelligent Orchestrator (`.claude/ORCHESTRATOR.md`)
- **Pattern Detection**: Automatically analyzes requests to understand intent and complexity
- **Wave Orchestration**: Multi-stage execution for complex operations (30-50% better results)
- **Auto-Activation**: Smart routing based on keywords, file patterns, and complexity
- **Quality Gates**: 8-step validation cycle ensuring code quality

**Key Features**:
- Complexity scoring (0.0-1.0 scale)
- Automatic flag activation based on context
- Resource management with 5 threshold zones
- Task delegation with performance gains up to 70%

### 2. AI Personas System (`.claude/PERSONAS.md`)
11 specialized AI personalities that auto-activate based on context:

- **`--persona-architect`**: Systems design, long-term architecture
- **`--persona-frontend`**: UI/UX, accessibility, performance
- **`--persona-backend`**: APIs, databases, reliability
- **`--persona-security`**: Threat modeling, compliance
- **`--persona-performance`**: Optimization, bottleneck elimination
- **`--persona-analyzer`**: Root cause analysis, investigation
- **`--persona-qa`**: Testing, quality assurance
- **`--persona-refactorer`**: Code quality, technical debt
- **`--persona-devops`**: Infrastructure, deployment
- **`--persona-mentor`**: Knowledge transfer, education
- **`--persona-scribe`**: Documentation, localization

**Auto-Activation Example**:
```bash
# Frontend work automatically activates frontend persona + Magic MCP
/wd:implement LoginComponent

# Security analysis automatically activates security persona + Sequential MCP
/wd:review auth-system --focus security
```

### 3. Specialized Agents (`.claude/AGENTS.md`)
5 domain-expert agents using Claude Code's native Task tool:

- **`wd-frontend-agent`**: UI/UX development (React, Vue, accessibility)
- **`wd-backend-agent`**: APIs, databases, microservices
- **`wd-security-agent`**: Vulnerability assessment, compliance
- **`wd-test-agent`**: E2E testing, quality assurance
- **`wd-docs-agent`**: Documentation, knowledge management

**Coordination Patterns**:
- **Parallel**: Independent analysis (3-5x faster)
- **Sequential**: Dependent workflows with handoffs
- **Hierarchical**: Central coordinator with specialists

### 4. MCP Server Integration (`.claude/MCP.md`)
Smart coordination of 4 MCP servers:

- **Context7**: Library documentation, best practices
- **Sequential**: Complex analysis, systematic debugging
- **Magic**: UI component generation
- **Playwright**: Browser automation, E2E testing

**Auto-Selection Example**:
```bash
# Automatically uses Context7 for library docs
/wd:implement --with react-query

# Automatically uses Magic for UI components
/wd:implement DashboardCard
```

### 5. Flag System (`.claude/FLAGS.md`)
Powerful flag system with auto-activation:

**Thinking Flags**:
- `--think`: Multi-file analysis (~4K tokens)
- `--think-hard`: System-wide analysis (~10K tokens)
- `--ultrathink`: Critical redesign (~32K tokens)

**Wave Flags**:
- `--wave-mode [auto|force|off]`: Control wave orchestration
- `--wave-strategy [progressive|systematic|adaptive|enterprise]`

**Agent Flags**:
- `--agent [name]`: Manual agent activation
- `--agents [list]`: Multi-agent coordination
- `--delegate [files|folders|auto]`: Task delegation

**MCP Flags**:
- `--c7` / `--context7`: Enable Context7
- `--seq` / `--sequential`: Enable Sequential
- `--magic`: Enable Magic
- `--play` / `--playwright`: Enable Playwright

### 6. Operational Modes (`.claude/MODES.md`)

**Task Management Mode**:
- Structured workflow execution
- Progress tracking with TodoWrite
- Single focus protocol (one active task)

**Introspection Mode** (`--introspect`):
- Meta-cognitive analysis
- Reasoning chain examination
- Framework compliance validation

**Token Efficiency Mode** (`--uc`):
- 30-50% token reduction
- Intelligent compression with quality preservation
- Symbol system and abbreviations

### 7. Development Principles (`.claude/PRINCIPLES.md`)
- SOLID principles
- Evidence-based decision making
- Quality-first philosophy
- Human-AI collaboration

### 8. Operational Rules (`.claude/RULES.md`)
- Task management rules
- File operation security
- Framework compliance
- Systematic codebase changes

## Usage Examples

### Basic Auto-Activation
```bash
# Automatically detects frontend work, activates frontend persona + Magic
/wd:implement UserProfile --type component

# Automatically detects security needs, activates security persona + Sequential
/wd:analyze auth-module --focus security
```

### Multi-Agent Coordination
```bash
# Parallel agents for comprehensive review
/wd:review --comprehensive --agents security,performance,quality

# Sequential workflow for full-stack feature
/wd:implement user-dashboard --agents frontend,backend,test,docs
```

### Wave Orchestration
```bash
# Force wave mode for complex refactoring
/wd:improve legacy-code --wave-mode force --wave-strategy systematic

# Enterprise-scale optimization
/wd:improve entire-app --wave-strategy enterprise
```

### Manual Control
```bash
# Explicit persona activation
/wd:implement API --persona-backend --seq --c7

# Explicit agent activation
/wd:implement PaymentForm --agent wd-frontend-agent --magic
```

## Performance Benefits

- **Wave Orchestration**: 30-50% better results through multi-stage execution
- **Agent Delegation**: 40-70% time savings for suitable operations
- **MCP Coordination**: 3-5x faster with parallel agent execution
- **Token Efficiency**: 30-50% token reduction with `--uc` mode

## Configuration

### Entry Point
All orchestration starts from `.claude/CLAUDE.md` which references:
- ORCHESTRATOR.md
- PERSONAS.md
- AGENTS.md
- FLAGS.md
- MCP.md
- MODES.md
- PRINCIPLES.md
- RULES.md

### Auto-Activation Thresholds
- **Wave Mode**: complexity ≥0.7 AND files >20 AND operation_types >2
- **Agent Delegation**: >7 directories OR >50 files OR complexity >0.8
- **Persona Activation**: Multi-factor scoring (keyword 40%, context 40%, history 20%, metrics 10%)

## Best Practices

1. **Trust Auto-Activation**: The system learns your patterns
2. **Use Flags Sparingly**: Let the orchestrator optimize
3. **Monitor Performance**: Review agent performance metrics
4. **Provide Context**: Detailed descriptions improve routing
5. **Combine Strategically**: Some tasks benefit from multi-agent coordination

## Troubleshooting

### Performance Issues
```bash
# Use introspection mode to analyze
/wd:analyze --introspect
```

### Quality Issues
```bash
# Enable safe mode for production
/wd:implement --safe-mode --validate
```

### Resource Constraints
```bash
# Enable ultra-compressed mode
/wd:implement --uc
```

## Learn More

- Read `.claude/ORCHESTRATOR.md` for routing intelligence
- Read `.claude/PERSONAS.md` for persona details
- Read `.claude/AGENTS.md` for agent capabilities
- Read `.claude/FLAGS.md` for complete flag reference
- Read `.claude/MCP.md` for MCP server coordination

---

**WD Framework v2.0** - Intelligent orchestration for modern web development
