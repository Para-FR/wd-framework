---
allowed-tools: [Read, Write, Edit, MultiEdit, Bash, Glob, TodoWrite, Task]
description: "Feature and code implementation with intelligent persona activation"
wave-enabled: true
category: "Development & Implementation"
auto-persona: ["frontend", "backend", "architect", "security"]
mcp-servers: ["magic", "context7", "sequential"]
---

# /wd:implement - Feature Implementation

## Purpose
Implement features, components, and code functionality with intelligent expert activation, comprehensive development support, and best practices enforcement.

## Usage
```bash
/wd:implement [feature-description] [--type <type>] [--framework <name>] [--<flags>]
```

## Arguments
- `[feature-description]` - Clear description of what to implement
- `--type component|api|service|feature|module` - Implementation type
- `--framework react|vue|angular|express|fastapi|etc` - Target framework
- `--safe` - Use conservative implementation approach
- `--iterative` - Enable iterative development with validation
- `--with-tests` - Include test implementation
- `--documentation` - Generate documentation alongside code
- `--agent <agent-name>` - Manually activate specific agent
- `--agents <agent-list>` - Activate multiple coordinated agents
- `--track quick|standard|enterprise` - Development track selection
- `--skill-level beginner|intermediate|expert` - Output verbosity
- `--yolo` - Automated execution mode
- `--story <file>` - Use story file as source of truth

## Auto-Activation Patterns

### Personas (Context-Dependent)
- **Frontend**: UI components, React/Vue/Angular development
  - Keywords: component, UI, React, Vue, responsive, accessibility
  - Files: `*.jsx`, `*.tsx`, `*.vue`, `*.css`

- **Backend**: APIs, services, database integration
  - Keywords: API, database, server, endpoint, authentication
  - Files: `*.js`, `*.ts`, `*.py`, `*.go`, `controllers/*`, `models/*`

- **Security**: Authentication, authorization, data protection
  - Keywords: auth, security, encryption, validation
  - Auto-activates for sensitive operations

- **Architect**: System design and module structure
  - Complex features requiring architectural decisions
  - Multi-component implementations

### MCP Servers
- **Magic**: Primary for UI component generation and design systems
- **Context7**: Framework documentation and implementation patterns
- **Sequential**: Complex business logic and multi-step workflows

### Agent Coordination
- **Single Domain**: Domain-specific agent (frontend, backend, etc.)
- **Multi-Domain**: Hierarchical coordination with multiple specialists
- **Testing**: Automatic test-agent activation with `--with-tests`
- **Documentation**: Automatic docs-agent activation with `--documentation`

## Execution Workflow

1. **Requirements Analysis**
   - Parse feature description and detect technology context
   - Identify required components and dependencies
   - Determine implementation complexity

2. **Persona & Agent Activation**
   - Auto-activate relevant personas based on context
   - Route to specialized agents when beneficial
   - Coordinate MCP servers for enhanced capabilities

3. **Implementation Phase**
   - Generate code with framework best practices
   - Apply security and quality validation
   - Follow project conventions and patterns
   - Use appropriate design patterns

4. **Testing & Validation**
   - Generate tests if requested
   - Validate against requirements
   - Check for common pitfalls and vulnerabilities

5. **Documentation & Next Steps**
   - Document implementation decisions
   - Provide usage examples
   - Suggest testing and integration steps

## BMAD Protocol

### Story File Discovery
1. Check for `.story.md` or `story.md` in project root
2. If found, use as single source of truth
3. Execute tasks in story-defined sequence

### ADR Consultation
1. Scan `docs/decisions/` or `.adr/` directory
2. Load relevant ADRs based on implementation domain
3. Reference decisions in code comments

### Track-Aware Execution
| Track | Phases |
|-------|--------|
| quick | Implement only |
| standard | Analyze → Plan → Implement → Validate |
| enterprise | + ADR creation + Adversarial review |

### Skill Level Output
| Level | Behavior |
|-------|----------|
| beginner | Detailed explanations, extensive comments |
| intermediate | Balanced context (default) |
| expert | Code-first, minimal commentary |

## Examples

```bash
# Frontend component with tests
/wd:implement LoginComponent --type component --framework react --with-tests

# Backend API with documentation
/wd:implement user-authentication-system --type feature --documentation

# Multi-agent full-stack feature
/wd:implement user-dashboard --agents frontend,backend,test,docs

# Safe iterative implementation
/wd:implement payment-processing-service --type service --safe --iterative

# Explicit agent selection
/wd:implement REST-API-users --type api --agent gd-backend-agent
```

## Integration Features

### Framework Detection
- Automatically detects project framework and conventions
- Adapts code style to existing patterns
- Uses project-specific dependencies

### Security-First
- Security persona auto-activates for sensitive operations
- Input validation by default
- OWASP compliance checks

### Quality Assurance
- Code quality validation
- Performance considerations
- Accessibility compliance (for UI components)

### Testing Integration
- Unit test generation
- Integration test suggestions
- E2E test strategies with Playwright agent

## Output Structure

```markdown
# Implementation: [Feature Name]

## Summary
- Type: [component|api|service|feature]
- Framework: [framework-name]
- Complexity: [low|medium|high]
- Estimated time: [time estimate]

## Files Created/Modified
- `path/to/file1.ts` - Description
- `path/to/file2.ts` - Description

## Implementation Details
[Code with explanations]

## Security Considerations
- [Security measure 1]
- [Security measure 2]

## Testing
- Unit tests: [location]
- Integration tests: [strategy]
- E2E tests: [recommendations]

## Next Steps
1. [Step 1]
2. [Step 2]
3. [Step 3]

## Documentation
[Usage examples and API documentation]
```

## Best Practices

### Code Quality
- Follow SOLID principles
- Use appropriate design patterns
- Maintain DRY principle
- Ensure proper error handling

### Performance
- Optimize critical paths
- Consider scalability
- Monitor resource usage
- Implement caching strategies

### Security
- Input validation
- Authentication/Authorization
- Secure data handling
- OWASP compliance

### Testing
- Comprehensive test coverage
- Edge case handling
- Integration testing
- Performance testing

## Related Commands
- `/wd:build` - Build and compile project
- `/wd:test` - Run test suite
- `/wd:improve` - Enhance existing implementation
- `/wd:review` - Code review before merge
- `/wd:document` - Generate documentation
