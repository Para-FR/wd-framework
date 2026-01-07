# ROUTING - Detection & Orchestration

## Complexity Classification

| Level | Indicators | Token Budget | Time |
|-------|------------|--------------|------|
| Simple | Single file, basic CRUD, <3 steps | 5K | <5min |
| Moderate | Multi-file, analysis, refactor, 3-10 steps | 15K | 5-30min |
| Complex | System-wide, architecture, >10 steps | 30K+ | >30min |

## Domain Detection

| Domain | Keywords | File Patterns |
|--------|----------|---------------|
| Frontend | UI, component, React, Vue, CSS, responsive | *.jsx, *.tsx, *.vue, *.css |
| Backend | API, database, server, endpoint, auth | *.js, *.ts, *.py, controllers/* |
| Security | vulnerability, auth, encryption, audit | *auth*, *security*, *.pem |
| Infra | deploy, Docker, CI/CD, monitoring | Dockerfile, *.yml, .github/* |
| Docs | document, README, wiki, guide | *.md, docs/*, README* |

## Operation Types

| Type | Verbs | Typical Tools |
|------|-------|---------------|
| Analysis | analyze, review, explain, investigate | Grep, Read, Sequential |
| Creation | create, build, implement, generate | Write, Magic, Context7 |
| Modification | update, refactor, improve, fix | Edit, MultiEdit, Sequential |
| Debugging | debug, fix, troubleshoot | Grep, Sequential, Playwright |
| Iterative | improve, refine, enhance, polish | Sequential, Edit, TodoWrite |

## Routing Table

| Pattern | Complexity | Auto-Activates | Confidence |
|---------|------------|----------------|------------|
| analyze architecture | complex | architect, --ultrathink, Sequential | 95% |
| create component | simple | frontend, Magic, --uc | 90% |
| implement feature | moderate | domain-specific, Context7, Sequential | 88% |
| implement API | moderate | backend, --seq, Context7 | 92% |
| fix bug | moderate | analyzer, --think, Sequential | 85% |
| optimize performance | complex | performance, --think-hard, Playwright | 90% |
| security audit | complex | security, --ultrathink, Sequential | 95% |
| write documentation | moderate | scribe, Context7 | 95% |

## Wave Orchestration

**Trigger**: complexity ≥0.7 AND files >20 AND operation_types >2

**Wave-Enabled Commands** (Tier 1): /analyze, /build, /implement, /improve
**Wave-Enabled Commands** (Tier 2): /design, /task

### Wave Strategies

| Strategy | Use Case | Pattern |
|----------|----------|---------|
| Progressive | Incremental enhancement | review → plan → implement → validate |
| Systematic | Comprehensive analysis | assess → design → execute → verify |
| Adaptive | Dynamic configuration | analyze → strategize → transform → optimize |
| Enterprise | Large-scale (>100 files) | coordinate → delegate → aggregate → verify |

### Wave Control

```yaml
activation:
  auto: complexity ≥0.7
  force: --wave-mode force
  disable: --single-wave | --wave-mode off

scoring:
  complexity: 0.2-0.4
  scale: 0.2-0.3
  operations: 0.2
  domains: 0.1
  flags: 0.05-0.1

threshold: 0.7 (default) | --wave-threshold custom
```

## Architecture Decision Records (ADR)

### When to Create
| Context | Trigger |
|---------|---------|
| API design | REST vs GraphQL, versioning |
| Database | Schema design, normalization |
| State | Redux vs Context vs Zustand |
| Styling | CSS modules vs Tailwind vs CSS-in-JS |
| Testing | Jest vs Vitest, E2E strategy |

### ADR Format
```markdown
# ADR-XXX: [Title]
## Context | ## Options Considered | ## Decision | ## Consequences
```

### Multi-Agent ADR Usage
- Agents MUST consult existing ADRs before implementation
- Prevents pattern conflicts in parallel execution
- Location: `docs/decisions/` or `.adr/`

## Development Tracks

| Track | Phases | Use When |
|-------|--------|----------|
| Quick | Plan → Implement | Bug fixes, config, complexity <0.3 |
| Standard | Analysis → Plan → Solution → Implement | Features, complexity 0.3-0.7 |
| Enterprise | All + ADR + Adversarial review | Architecture, security, complexity >0.7 |

### Track Selection
```yaml
quick: skip [analysis, solutioning] | trigger: complexity <0.3 OR single-file
standard: all phases | trigger: complexity 0.3-0.7 (default)
enterprise: +adr +adversarial-review +docs | trigger: complexity >0.7 OR security-critical
```

## Agent Delegation

**Trigger**: >7 directories OR >50 files OR complexity >0.8

### Coordination Patterns

| Pattern | Trigger | Agents | Execution |
|---------|---------|--------|-----------|
| Parallel | independent analysis | domain specialists | simultaneous |
| Sequential | dependent tasks | pipeline stages | handoff |
| Hierarchical | complex migration | coordinator + specialists | managed |

### Agent-Command Matrix

| Command | Primary Agent | Secondary | Pattern |
|---------|---------------|-----------|---------|
| /implement | domain-specific | test-agent | sequential |
| /review | security-agent | test, docs | parallel |
| /migrate | frontend/backend | test, docs | hierarchical |
| /finalize | docs-agent | security | sequential |

## Auto-Triggers

```yaml
delegation:
  dirs >7: --delegate --parallel-dirs
  files >50 & complexity >0.6: --delegate --sub-agents
  domains >3: --delegate --parallel-focus

waves:
  complexity >0.8 & files >20 & types >2: --wave-count 5
  domains >3 & tokens >15K: --adaptive-waves
  production | security_audit: --wave-validation
  files >100 & complexity >0.7: --enterprise-waves

loops:
  keywords [polish, refine, enhance]: --loop
  keywords [iteratively, step by step]: --loop
```

## Precedence Rules

1. Safety flags (--safe-mode) > optimization flags
2. Explicit flags > auto-activation
3. Thinking: --ultrathink > --think-hard > --think
4. --no-mcp overrides all MCP flags
5. Scope: system > project > module > file
6. Last persona takes precedence
7. Wave: off > force > auto
8. Delegation: explicit > auto-detection
9. --uc auto-activation overrides verbose

## Confidence Scoring

| Factor | Weight |
|--------|--------|
| Pattern match | 40% |
| Historical success | 30% |
| Context completeness | 20% |
| Resource availability | 10% |
