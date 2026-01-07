# WORKFLOWS - Execution Patterns

## Story File Pattern

### Purpose
Single source of truth for task execution

### Structure
```markdown
# Story: [Title]

## Context
[Background and requirements]

## Tasks
1. [ ] Task 1 - description
2. [ ] Task 2 - description

## Acceptance Criteria
- [ ] Criterion 1
- [ ] Criterion 2

## ADR References
- ADR-001: [Link]
```

### Execution Rules
1. Read ENTIRE story file before implementing
2. Execute tasks in SPECIFIED order (no skipping)
3. NEVER proceed with failing tests
4. NEVER lie about test status
5. Update task checkboxes as completed

### Discovery
Check for: `.story.md` | `story.md` | `STORY.md` in project root

## Document Sharding

### Token Reduction Strategy
~90% reduction for large documents

| Strategy | File Size | Approach |
|----------|-----------|----------|
| FULL_LOAD | <5KB | Load entirely |
| SELECTIVE_LOAD | 5-50KB | Load relevant sections |
| INDEX_GUIDED | >50KB | Index first, load on-demand |

### Sharding Process
1. Parse document structure (## headings)
2. Generate section index with metadata
3. Load sections based on query context
4. Recompose for coherent output

### Auto-Trigger
- File count >50: enable INDEX_GUIDED
- Single large file >50KB: enable SELECTIVE_LOAD
- Flag: `--sharding auto|full|selective|index`

## Adversarial Review

### Trigger Conditions
- Risk score >0.7
- Security-critical changes
- Production deployments
- `--review-adversarial` flag

### Review Process
1. Implementation complete
2. Switch to adversarial perspective
3. Challenge assumptions
4. Identify edge cases
5. Validate security implications
6. Document findings

### Adversarial Checklist
- [ ] Input validation gaps?
- [ ] Authentication/authorization bypasses?
- [ ] Data exposure risks?
- [ ] Performance edge cases?
- [ ] Failure mode handling?

## YOLO Mode Execution

### When Enabled
- `--yolo` flag explicitly set
- Simulates expert user responses
- Minimal checkpoints

### Behavior
- Auto-confirm non-critical decisions
- Skip explanation sections
- Direct implementation path
- Still enforces security gates

### Safety Rails (NOT skippable)
- Security validation required
- Test execution required
- Git commits require explicit confirmation
- Production deployments blocked

## Session Continuity

### Frontmatter Tracking
```yaml
workflow: /wd:implement
current_step: 3
total_steps: 7
status: in_progress
context: ["files_read", "patterns_identified"]
last_checkpoint: 2024-01-07T10:30:00Z
```

### Resume Protocol
1. Check for existing frontmatter
2. Load accumulated context
3. Continue from last checkpoint
4. Maintain progress tracking

### Cross-Session State
- Tasks persist via /task command
- Context accumulates across waves
- ADR references preserved
- Test results tracked
