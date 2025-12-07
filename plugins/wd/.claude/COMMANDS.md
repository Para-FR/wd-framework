# COMMANDS.md - WD Framework Command Execution Framework

Command execution framework for Claude Code WD Framework integration.

## Command System Architecture

### Core Command Structure
```yaml
---
command: "/wd:{command-name}"
category: "Primary classification"
purpose: "Operational objective"
wave-enabled: true|false
performance-profile: "optimization|standard|complex"
---
```

### Command Processing Pipeline
1. **Input Parsing**: `$ARGUMENTS` with `@<path>`, `!<command>`, `--<flags>`
2. **Context Resolution**: Auto-persona activation and MCP server selection
3. **Wave Eligibility**: Complexity assessment and wave mode determination
4. **Execution Strategy**: Tool orchestration and resource allocation
5. **Quality Gates**: Validation checkpoints and error handling

### Integration Layers
- **Claude Code**: Native slash command compatibility
- **Persona System**: Auto-activation based on command context
- **MCP Servers**: Context7, Sequential, Magic, Playwright integration
- **Wave System**: Multi-stage orchestration for complex operations

## Wave System Integration

**Wave Orchestration Engine**: Multi-stage command execution with compound intelligence. Auto-activates on complexity ≥0.7 + files >20 + operation_types >2.

**Wave-Enabled Commands**:
- **Tier 1**: `/wd:analyze`, `/wd:build`, `/wd:implement`, `/wd:improve`
- **Tier 2**: `/wd:design`, `/wd:task`

### Development Commands

**`/wd:build $ARGUMENTS`**
```yaml
---
command: "/wd:build"
category: "Development & Deployment"
purpose: "Project builder with framework detection"
wave-enabled: true
performance-profile: "optimization"
---
```
- **Auto-Persona**: Frontend, Backend, Architect, Scribe
- **MCP Integration**: Magic (UI builds), Context7 (patterns), Sequential (logic)
- **Tool Orchestration**: [Read, Grep, Glob, Bash, TodoWrite, Edit, MultiEdit]
- **Arguments**: `[target]`, `@<path>`, `!<command>`, `--<flags>`

**`/wd:implement $ARGUMENTS`**
```yaml
---
command: "/wd:implement"
category: "Development & Implementation"
purpose: "Feature and code implementation with intelligent persona activation"
wave-enabled: true
performance-profile: "standard"
---
```
- **Auto-Persona**: Frontend, Backend, Architect, Security (context-dependent)
- **MCP Integration**: Magic (UI components), Context7 (patterns), Sequential (complex logic)
- **Tool Orchestration**: [Read, Write, Edit, MultiEdit, Bash, Glob, TodoWrite, Task]
- **Arguments**: `[feature-description]`, `--type component|api|service|feature`, `--framework <name>`, `--<flags>`


### Analysis Commands

**`/wd:analyze $ARGUMENTS`**
```yaml
---
command: "/wd:analyze"
category: "Analysis & Investigation"
purpose: "Multi-dimensional code and system analysis"
wave-enabled: true
performance-profile: "complex"
---
```
- **Auto-Persona**: Analyzer, Architect, Security
- **MCP Integration**: Sequential (primary), Context7 (patterns), Magic (UI analysis)
- **Tool Orchestration**: [Read, Grep, Glob, Bash, TodoWrite]
- **Arguments**: `[target]`, `@<path>`, `!<command>`, `--<flags>`

**`/wd:troubleshoot [symptoms] [flags]`** - Problem investigation | Auto-Persona: Analyzer, QA | MCP: Sequential, Playwright

**`/wd:explain [topic] [flags]`** - Educational explanations | Auto-Persona: Mentor, Scribe | MCP: Context7, Sequential


### Quality Commands

**`/wd:improve [target] [flags]`**
```yaml
---
command: "/wd:improve"
category: "Quality & Enhancement"
purpose: "Evidence-based code enhancement"
wave-enabled: true
performance-profile: "optimization"
---
```
- **Auto-Persona**: Refactorer, Performance, Architect, QA
- **MCP Integration**: Sequential (logic), Context7 (patterns), Magic (UI improvements)
- **Tool Orchestration**: [Read, Grep, Glob, Edit, MultiEdit, Bash]
- **Arguments**: `[target]`, `@<path>`, `!<command>`, `--<flags>`


**`/wd:cleanup [target] [flags]`** - Project cleanup and technical debt reduction | Auto-Persona: Refactorer | MCP: Sequential

### Additional Commands

**`/wd:document [target] [flags]`** - Documentation generation | Auto-Persona: Scribe, Mentor | MCP: Context7, Sequential

**`/wd:finalize [message] [flags]`**
```yaml
---
command: "/wd:finalize"
category: "Workflow & Automation"
purpose: "Complete project finalization with quality gates and git workflow"
wave-enabled: false
performance-profile: "optimization"
---
```
- **Auto-Persona**: DevOps, QA, Scribe (message generation)
- **MCP Integration**: Sequential (workflow coordination), Context7 (best practices)
- **Tool Orchestration**: [Bash, Read, Edit, TodoWrite]
- **Workflow Pipeline**:
  1. Update documentation (.md files) with latest changes
  2. Detect Next.js version from package.json
  3. **If Next.js < 16**: Run `bun lint` for code quality validation
  4. Run `bun type` for TypeScript type checking
  5. Run `bun build` for compilation verification
  6. Generate structured commit message if not provided
  7. Git add, commit, and push if all gates pass
- **Arguments**: `[commit-message]`, `--skip-docs`, `--skip-lint`, `--skip-types`, `--skip-build`, `--dry-run`, `--no-push`
- **Note**: Next.js 16+ removed `next lint`. Auto-detects version and skips linting for Next.js 16+.

**`/wd:estimate [target] [flags]`** - Evidence-based estimation | Auto-Persona: Analyzer, Architect | MCP: Sequential, Context7

**`/wd:task [operation] [flags]`** - Long-term project management | Auto-Persona: Architect, Analyzer | MCP: Sequential

**`/wd:test [type] [flags]`** - Testing workflows | Auto-Persona: QA | MCP: Playwright, Sequential

**`/wd:git [operation] [flags]`** - Git workflow assistant | Auto-Persona: DevOps, Scribe, QA | MCP: Sequential

**`/wd:design [domain] [flags]`** - Design orchestration | Auto-Persona: Architect, Frontend | MCP: Magic, Sequential, Context7

**`/wd:brainstorm [topic] [flags]`**
```yaml
---
command: "/wd:brainstorm"
category: "Planning & Ideation"
purpose: "Structured idea generation and solution exploration"
wave-enabled: true
performance-profile: "complex"
---
```
- **Auto-Persona**: Mentor, Architect, Analyzer
- **MCP Integration**: Sequential (structured thinking), Context7 (research patterns)
- **Tool Orchestration**: [Sequential, Read, Write, TodoWrite]
- **Arguments**: `[topic]`, `--format json|markdown|mindmap`, `--depth shallow|deep|comprehensive`, `--export <path>`

**`/wd:review [target] [flags]`**
```yaml
---
command: "/wd:review"
category: "Quality & Analysis"
purpose: "Comprehensive code and system review with actionable insights"
wave-enabled: true
performance-profile: "complex"
---
```
- **Auto-Persona**: QA, Security, Performance, Analyzer
- **MCP Integration**: Sequential (systematic analysis), Context7 (best practices), Playwright (E2E validation)
- **Tool Orchestration**: [Read, Grep, Glob, Sequential, TodoWrite]
- **Arguments**: `[target]`, `--focus security|performance|quality|architecture`, `--format report|checklist|metrics`, `--export <path>`

**`/wd:migrate [source] [target] [flags]`**
```yaml
---
command: "/wd:migrate"
category: "Development & Transformation"
purpose: "Code migration between frameworks and technologies"
wave-enabled: true
performance-profile: "complex"
---
```
- **Auto-Persona**: Architect, Frontend, Backend (context-dependent)
- **MCP Integration**: Context7 (framework patterns), Sequential (migration planning), Magic (UI migration)
- **Tool Orchestration**: [Read, Write, Edit, MultiEdit, Context7, TodoWrite]
- **Arguments**: `[source-framework]`, `[target-framework]`, `--strategy incremental|complete|hybrid`, `--validate`, `--backup`

**`/wd:benchmark [target] [flags]`**
```yaml
---
command: "/wd:benchmark"
category: "Performance & Testing"
purpose: "Performance testing and optimization with visual reports"
wave-enabled: false
performance-profile: "optimization"
---
```
- **Auto-Persona**: Performance, QA
- **MCP Integration**: Playwright (performance metrics), Sequential (analysis)
- **Tool Orchestration**: [Playwright, Read, Write, Bash, TodoWrite]
- **Arguments**: `[target]`, `--metrics performance|accessibility|seo|all`, `--compare <baseline>`, `--export <path>`

### Meta & Orchestration Commands

**`/wd:index [query] [flags]`** - Command catalog browsing | Auto-Persona: Mentor, Analyzer | MCP: Sequential

**`/wd:load [path] [flags]`** - Project context loading | Auto-Persona: Analyzer, Architect, Scribe | MCP: All servers

**Iterative Operations** - Use `--loop` flag with improvement commands for iterative refinement

**`/wd:spawn [mode] [flags]`** - Task orchestration | Auto-Persona: Analyzer, Architect, DevOps | MCP: All servers

### ERP Commands

**`/orvi-agent fix-bug [bugId] [context] [flags]`**
```yaml
---
command: "/orvi-agent"
category: "ERP & Bug Management" 
purpose: "Automated bug analysis and fixing for Orvi ERP system with MongoDB integration"
wave-enabled: false
performance-profile: "standard"
---
```
- **Auto-Persona**: Analyzer, Backend, QA, DevOps
- **MCP Integration**: Sequential (bug analysis), Context7 (framework patterns), Playwright (validation)
- **Tool Orchestration**: [Read, Grep, Glob, Edit, MultiEdit, Bash, TodoWrite, Task]
- **MongoDB Integration**: Direct connection to Orvi ERP bugreports collection
- **Multi-Agent Workflow**: Analysis → Fix → Test → Validate → Database Update
- **Arguments**: `[bugId]` (required 24-char MongoDB ObjectId), `[context]` (optional), `--strategy auto|deep|quick`, `--dry-run`, `--think-hard`, `--no-update-db`, `--verbose`

## Command Execution Matrix

### Performance Profiles
```yaml
optimization: "High-performance with caching and parallel execution"
standard: "Balanced performance with moderate resource usage"
complex: "Resource-intensive with comprehensive analysis"
```

### Command Categories
- **Development**: build, implement, design, migrate
- **Planning**: brainstorm, workflow, estimate, task
- **Analysis**: analyze, review, troubleshoot, explain
- **Quality**: improve, cleanup
- **Testing**: test, benchmark
- **Documentation**: document
- **Workflow**: finalize
- **Version-Control**: git
- **ERP**: orvi-agent
- **Meta**: index, load, spawn

### Wave-Enabled Commands
10 commands: `/wd:analyze`, `/wd:build`, `/wd:brainstorm`, `/wd:design`, `/wd:implement`, `/wd:improve`, `/wd:migrate`, `/wd:review`, `/wd:task`, `/wd:workflow`

