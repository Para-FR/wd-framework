# CORE - Principles & Rules

## Design Principles

**SOLID**: S=single responsibility | O=open/closed | L=Liskov substitution | I=interface segregation | D=dependency inversion

**Core**: DRY | KISS | YAGNI | Composition > inheritance | Loose coupling | High cohesion

## Operational Rules

### Must Do
- Read → Write/Edit (always read before modify)
- Absolute paths only
- Batch tool calls when independent
- Validate before execute, verify after
- Check package.json before external libs
- Follow existing project patterns
- Complete discovery before codebase changes
- ≥90% context retention across operations

### Must Not
- Skip Read operations
- Use relative paths
- Auto-commit without permission
- Ignore framework patterns
- Mix user content in config
- Override safety protocols
- Make reactive changes without discovery

## Quality Gates

| Step | Check | Target |
|------|-------|--------|
| 1 | Syntax | Parser valid |
| 2 | Types | TS strict pass |
| 3 | Lint | 0 errors |
| 4 | Security | OWASP compliant |
| 5 | Tests | ≥80% unit, ≥70% integration |
| 6 | Performance | Budget targets met |
| 7 | Docs | Complete & accurate |
| 8 | Integration | E2E pass |

## Task Management

**States**: pending 📋 | in_progress 🔄 (max 1) | blocked 🚧 | completed ✅

**Flow**: TodoRead → TodoWrite(3+ tasks) → Execute → Track → Verify

**Layers**:
- L1: TodoWrite (session tasks)
- L2: /task (multi-session features)
- L3: /spawn (complex orchestration)
- L4: /loop (iterative refinement)

## Progressive Disclosure

### Workflow Execution
- Step-by-step: step-01 → step-02 → step-N (no skip/optimization)
- Checkpoint gates require confirmation before progression
- Session continuity via frontmatter tracking
- Context accumulation across steps

### Story File Pattern (Single Source of Truth)
Story file defines: task sequence (authoritative) | acceptance criteria | constraints | ADR refs

**Rules**:
1. Read ENTIRE story file before implementing
2. Execute tasks in SPECIFIED order
3. NEVER proceed with failing tests
4. NEVER lie about test status

### Session Frontmatter
```yaml
workflow: /wd:implement
current_step: 3
total_steps: 7
status: in_progress
context: ["files_read", "patterns_identified"]
```

## Decision Framework

**Priority**: Safety > correctness > performance > convenience

**Risk Score**: complexity×0.3 + vulnerabilities×0.25 + resources×0.2 + failure_prob×0.15 + time×0.1

**Actions**: Score >0.7 → validation required | >0.8 → safe mode suggested

## Resource Thresholds

| Zone | Usage | Action |
|------|-------|--------|
| Green | 0-60% | Full operations |
| Yellow | 60-75% | Enable --uc mode |
| Orange | 75-85% | Defer non-critical |
| Red | 85-95% | Force efficiency |
| Critical | 95%+ | Essential only |

## Error Handling

**Pattern**: Fail fast, fail explicitly | Never suppress silently | Preserve context | Design for recovery

**Recovery**: Exponential backoff → Circuit breaker → Graceful degradation → Alternative routing
