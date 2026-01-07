---
allowed-tools: [Read, Grep, Glob, Bash, TodoWrite, Task]
description: "Multi-dimensional code and system analysis with intelligent routing"
wave-enabled: true
category: "Analysis & Investigation"
auto-persona: ["analyzer", "architect", "security"]
mcp-servers: ["sequential", "context7", "magic"]
---

# /wd:analyze - Comprehensive Analysis

## Purpose
Execute comprehensive code analysis across quality, security, performance, and architecture domains with intelligent persona activation and MCP integration.

## Usage
```bash
/wd:analyze [target] [@<path>] [!<command>] [--<flags>]
```

## Arguments
- `[target]` - Files, directories, or project to analyze
- `@<path>` - Specific path or file pattern
- `!<command>` - Run command before analysis
- `--focus quality|security|performance|architecture` - Analysis focus area
- `--depth quick|deep|comprehensive` - Analysis depth
- `--format text|json|report|markdown` - Output format
- `--wave-mode auto|force|off` - Wave orchestration control
- `--delegate files|folders|auto` - Sub-agent delegation strategy
- `--sharding auto|full|selective|index` - Document loading strategy
- `--facilitation` - Enable guided discovery mode

## Auto-Activation Patterns

### Personas
- **Analyzer**: Root cause specialist (primary)
- **Architect**: System design and structure
- **Security**: Vulnerability assessment
- **Performance**: Bottleneck identification

### MCP Servers
- **Sequential**: Primary for systematic analysis
- **Context7**: Best practices and patterns
- **Magic**: UI component analysis

### Wave Orchestration
- **Trigger**: complexity ≥0.7 AND files >20 AND operation_types >2
- **Strategy**: Systematic methodical analysis
- **Phases**: Discovery → Analysis → Synthesis → Recommendations

## Execution Workflow

1. **Discovery Phase**
   - Glob for systematic file discovery
   - Categorize by type and complexity
   - Identify dependencies and relationships

2. **Analysis Phase**
   - Apply domain-specific analysis techniques
   - Grep for pattern-based analysis
   - Read for deep code inspection
   - Coordinate MCP servers for specialized insights

3. **Synthesis Phase**
   - Aggregate findings across domains
   - Rate severity and priority
   - Identify patterns and anti-patterns

4. **Reporting Phase**
   - Generate comprehensive analysis report
   - Create actionable recommendations
   - Provide priority-ordered improvements

## Examples

```bash
# Quick security analysis
/wd:analyze auth-module --focus security --depth quick

# Comprehensive system analysis with wave mode
/wd:analyze @src/ --depth comprehensive --wave-mode force

# Performance bottleneck analysis
/wd:analyze --focus performance --delegate auto

# Multi-domain analysis with custom format
/wd:analyze entire-project --format report --depth deep
```

## Document Sharding

For large codebases (>50 files):

| Strategy | File Size | Approach |
|----------|-----------|----------|
| FULL_LOAD | <5KB | Load entirely |
| SELECTIVE_LOAD | 5-50KB | Load relevant sections |
| INDEX_GUIDED | >50KB | Index first, load on-demand |

### Auto-Trigger
- File count >50: enable INDEX_GUIDED
- `--sharding auto`: intelligent selection
- ~90% token reduction vs. full load

## Integration Features

- **Quality Gates**: Applies 8-step validation cycle
- **Evidence-Based**: All findings backed by code references
- **Actionable**: Clear next steps with effort estimates
- **Contextual**: Adapts to project type and technology stack
- **Sharding**: Efficient large codebase handling

## Output Structure

```markdown
# Analysis Report: [Target]

## Executive Summary
- Total files analyzed: X
- Findings by severity: Critical (X), High (X), Medium (X), Low (X)
- Top 3 priorities with effort estimates

## Domain Analysis
### Quality
- Code quality metrics
- Maintainability index
- Technical debt estimate

### Security
- Vulnerability assessment
- Security hotspots
- Compliance status

### Performance
- Bottleneck identification
- Resource usage analysis
- Optimization opportunities

### Architecture
- Structure analysis
- Dependency review
- Design patterns

## Recommendations
1. [Priority 1]: Description with implementation steps
2. [Priority 2]: Description with implementation steps
...
```

## Related Commands
- `/wd:improve` - Apply recommended improvements
- `/wd:review` - Comprehensive code review
- `/wd:troubleshoot` - Debug specific issues
- `/wd:estimate` - Estimate implementation effort
