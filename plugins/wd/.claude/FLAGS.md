# FLAGS - Reference

## Priority Order

1. Safety (--safe-mode) > optimization
2. Explicit > auto-activation
3. --ultrathink > --think-hard > --think
4. --no-mcp overrides all MCP flags
5. Scope: system > project > module > file
6. Last persona takes precedence
7. Wave: off > force > auto
8. --uc auto-activation overrides verbose

## Planning & Analysis

| Flag | Tokens | Auto-Trigger | Enables |
|------|--------|--------------|---------|
| --think | ~4K | Import chains >5, cross-module >10 | --seq, suggests analyzer |
| --think-hard | ~10K | System refactor, bottlenecks >3 modules | --seq --c7, suggests architect |
| --ultrathink | ~32K | Legacy modernization, critical vulns | --seq --c7 --all-mcp |
| --plan | - | Manual | Shows execution plan |

## Efficiency

| Flag | Effect | Auto-Trigger |
|------|--------|--------------|
| --uc / --ultracompressed | 30-50% token reduction | Context >75%, large ops |
| --answer-only | Direct response, no workflow | Manual only |
| --validate | Pre-op validation, risk assessment | Risk >0.7, resources >75% |
| --safe-mode | Max validation, conservative | Resources >85%, production |
| --verbose | Max detail | Manual only |

## Skill & Execution Mode

| Flag | Effect | Auto-Trigger |
|------|--------|--------------|
| --skill-level [level] | beginner\|intermediate\|expert | User preference |
| --yolo | Automated execution, minimal checkpoints | Manual only |
| --guided | Facilitation mode, strategic questions | Default |
| --strict | Validation at every step | Security ops |

### Skill Level Behavior
| Level | Explanations | Examples | Comments |
|-------|--------------|----------|----------|
| beginner | Detailed, why > what | Extended | Verbose |
| intermediate | Balanced | Relevant | Moderate |
| expert | Minimal | Code-only | None |

## Track Control

| Flag | Effect | Auto-Trigger |
|------|--------|--------------|
| --track quick | Skip analysis/solutioning | complexity <0.3 |
| --track standard | All phases | Default |
| --track enterprise | Extended reviews + ADRs | complexity >0.7 |

## Facilitation Mode

| Flag | Effect |
|------|--------|
| --facilitation | Enable guided discovery over generation |
| --discovery | Question-first approach before solutions |

## MCP Control

| Flag | Server | Auto-Trigger |
|------|--------|--------------|
| --c7 / --context7 | Context7 | External imports, framework Qs |
| --seq / --sequential | Sequential | Complex debug, --think flags |
| --magic | Magic | UI components, design |
| --play / --playwright | Playwright | Testing, E2E, perf |
| --all-mcp | All | complexity >0.8, multi-domain |
| --no-mcp | None | Manual, 40-60% faster |
| --no-[server] | Disable specific | Manual |

## Agent Control

| Flag | Effect |
|------|--------|
| --agent [name] | Activate specific agent |
| --agents [list] | Activate multiple (comma-separated) |
| --multi-agent [mode] | Coordination: auto\|parallel\|sequential\|hierarchical |
| --delegate [type] | Delegation: files\|folders\|auto |
| --agent-coordination [mode] | strict\|flexible\|autonomous |
| --concurrency [n] | Max concurrent agents (1-15, default 7) |

## Wave Control

| Flag | Effect | Auto-Trigger |
|------|--------|--------------|
| --wave-mode [mode] | auto\|force\|off | complexity ≥0.7 + files >20 |
| --wave-strategy [type] | progressive\|systematic\|adaptive\|enterprise | Project characteristics |
| --wave-delegation [type] | files\|folders\|tasks | Operation type |
| --wave-count [n] | Number of waves | complexity >0.8 + files >20 |
| --wave-validation | Enable wave-boundary validation | production, security |
| --wave-threshold [n] | Custom trigger threshold | Default 0.7 |

## Scope & Focus

| Flag | Options |
|------|---------|
| --scope | file \| module \| project \| system |
| --focus | performance \| security \| quality \| architecture \| accessibility \| testing |

## Iterative

| Flag | Effect |
|------|--------|
| --loop | Enable iterative mode |
| --iterations [n] | Cycle count (1-10, default 3) |
| --interactive | User confirmation between iterations |

## Personas

| Flag | Identity |
|------|----------|
| --persona-architect | Systems architecture |
| --persona-frontend | UX specialist |
| --persona-backend | Reliability engineer |
| --persona-analyzer | Root cause specialist |
| --persona-security | Threat modeler |
| --persona-mentor | Knowledge transfer |
| --persona-refactorer | Code quality |
| --persona-performance | Optimization |
| --persona-qa | Quality advocate |
| --persona-devops | Infrastructure |
| --persona-scribe=lang | Documentation (en,es,fr,de,ja,zh,pt,it,ru,ko) |

## Introspection

| Flag | Effect |
|------|--------|
| --introspect | Deep transparency mode |

**Markers**: 🤔 Thinking | 🎯 Decision | ⚡ Action | 📊 Check | 💡 Learning

## Auto-Activation Summary

```yaml
# Context-Based
Performance issues → --persona-performance --focus performance --think
Security concerns → --persona-security --focus security --validate
UI/UX tasks → --persona-frontend --magic --c7
Complex debugging → --think --seq --persona-analyzer
Large codebase → --uc + --delegate auto
Testing → --persona-qa --play --validate
DevOps → --persona-devops --safe-mode --validate
Refactoring → --persona-refactorer --wave-strategy systematic

# Skill-Based
new user detected → --skill-level beginner
repeated similar tasks → --skill-level expert
educational context → --skill-level beginner --guided

# Track-Based
single file change → --track quick
multi-file feature → --track standard
architecture/security → --track enterprise

# Scale-Based
dirs >7 → --delegate --parallel-dirs
files >50 & complexity >0.6 → --delegate --sub-agents
domains >3 → --delegate --parallel-focus
complexity >0.8 & scope=comprehensive → --delegate --focus-agents
tokens >20K → --delegate --aggregate-results

# Wave-Based
complexity ≥0.7 + files >20 + types >2 → --wave-mode auto
files >100 + complexity >0.7 + domains >2 → --enterprise-waves
production | security_audit → --wave-validation
```

## Conflict Resolution

| Conflict | Resolution |
|----------|------------|
| --verbose + --uc | --uc wins (auto-activated) |
| --no-mcp + --c7 | --no-mcp wins |
| --wave-mode off + auto-trigger | off wins |
| Multiple personas | Last specified wins |
