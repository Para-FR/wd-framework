# COMMANDS - Reference

## Command Matrix

| Command | Category | Wave | Personas | MCP | Tools |
|---------|----------|------|----------|-----|-------|
| /wd:analyze | Analysis | ✅ | analyzer, architect, security | Sequential, Context7 | Read, Grep, Glob, Bash, TodoWrite |
| /wd:build | Development | ✅ | frontend, backend, architect | Magic, Context7, Sequential | Read, Grep, Glob, Bash, Edit |
| /wd:implement | Development | ✅ | frontend, backend, architect, security | Magic, Context7, Sequential | Read, Write, Edit, Bash, Task |
| /wd:improve | Quality | ✅ | refactorer, performance, architect | Sequential, Context7, Magic | Read, Grep, Glob, Edit |
| /wd:design | Planning | ✅ | architect, frontend | Magic, Sequential, Context7 | Read, Write, TodoWrite |
| /wd:task | Meta | ✅ | architect, analyzer | Sequential | Read, Write, TodoWrite, Task |
| /wd:review | Quality | ✅ | qa, security, performance | Sequential, Context7, Playwright | Read, Grep, Glob |
| /wd:migrate | Development | ✅ | architect, frontend, backend | Context7, Sequential, Magic | Read, Write, Edit, TodoWrite |
| /wd:brainstorm | Planning | ✅ | mentor, architect, analyzer | Sequential, Context7 | Read, Write, TodoWrite |
| /wd:workflow | Planning | ✅ | architect, analyzer, devops | Sequential, Context7 | Read, Write, TodoWrite, Task |
| /wd:troubleshoot | Analysis | ❌ | analyzer, qa | Sequential, Playwright | Read, Grep, Bash |
| /wd:explain | Analysis | ❌ | mentor, scribe | Context7, Sequential | Read |
| /wd:cleanup | Quality | ❌ | refactorer | Sequential | Read, Edit, Grep |
| /wd:document | Docs | ❌ | scribe, mentor | Context7, Sequential | Read, Write |
| /wd:finalize | Workflow | ❌ | devops, qa, scribe | Sequential, Context7 | Bash, Read, Edit |
| /wd:estimate | Planning | ❌ | analyzer, architect | Sequential, Context7 | Read, Grep |
| /wd:test | Testing | ❌ | qa | Playwright, Sequential | Bash, Read, Write |
| /wd:benchmark | Testing | ❌ | performance, qa | Playwright, Sequential | Bash, Read, Write |
| /wd:git | Workflow | ❌ | devops, scribe, qa | Sequential | Bash, Read |
| /wd:index | Meta | ❌ | mentor, analyzer | Sequential | Read |
| /wd:load | Meta | ❌ | analyzer, architect | All | Read, Glob, Grep |
| /wd:spawn | Meta | ❌ | analyzer, architect, devops | All | Task, TodoWrite |

## Command Syntax

```
/wd:{command} [target] [@path] [!cmd] [--flags]

Arguments:
  [target]   - Files, directories, or description
  @<path>    - Specific path or pattern
  !<command> - Run command before execution
  --<flags>  - Modifier flags (see FLAGS.md)
```

## Category Quick Reference

### Development
- **build**: Project builder, framework detection, optimization
- **implement**: Feature/code implementation, persona activation
- **migrate**: Code migration between frameworks/technologies

### Analysis
- **analyze**: Multi-dimensional code/system analysis
- **troubleshoot**: Problem investigation, root cause
- **explain**: Educational explanations

### Quality
- **improve**: Evidence-based code enhancement
- **cleanup**: Technical debt reduction
- **review**: Comprehensive code review

### Testing
- **test**: Testing workflows, coverage
- **benchmark**: Performance testing, visual reports

### Planning
- **design**: System architecture, APIs, components
- **brainstorm**: Idea generation, solution exploration
- **estimate**: Evidence-based estimation
- **workflow**: PRD → implementation workflows

### Docs
- **document**: Documentation generation

### Workflow
- **finalize**: Quality gates, git workflow, deployment
- **git**: Git workflow assistant

### Meta
- **index**: Command catalog browsing
- **load**: Project context loading
- **spawn**: Task orchestration, multi-agent
- **task**: Long-term project management

## /wd:finalize Pipeline

1. Update docs (.md files)
2. Detect Next.js version
3. If Next.js <16: `bun lint`
4. `bun type` (TypeScript)
5. `bun build` (compile)
6. Generate commit message
7. Git add, commit, push (if gates pass)

**Flags**: `--skip-docs`, `--skip-lint`, `--skip-types`, `--skip-build`, `--dry-run`, `--no-push`

## Performance Profiles

| Profile | Description | Commands |
|---------|-------------|----------|
| optimization | High-perf, caching, parallel | build, improve, finalize, benchmark |
| standard | Balanced resources | implement, troubleshoot |
| complex | Resource-intensive, comprehensive | analyze, brainstorm, review, migrate, workflow |

## Common Patterns

```bash
# Quick analysis
/wd:analyze @src/ --focus security --depth quick

# Feature implementation with tests
/wd:implement LoginComponent --type component --with-tests

# Multi-agent review
/wd:review --comprehensive --agents security,performance,quality

# Iterative improvement
/wd:improve @module/ --loop --iterations 3

# Full workflow from PRD
/wd:workflow docs/prd.md --strategy systematic --c7 --sequential
```
