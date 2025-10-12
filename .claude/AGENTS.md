# AGENTS.md - WD Agent System Reference

Agent delegation system for Claude Code WD framework using native Task tool integration.

## Overview

The WD Agent System leverages Claude Code's native Task tool to create specialized sub-agents that can work autonomously or in coordination. Unlike external AI models, these are intelligent task delegation patterns optimized for specific domains.

**Core Features**:
- **Task Tool Integration**: Uses Claude Code's native Task tool for sub-agent delegation
- **Domain Specialization**: Agents optimized for specific technical domains
- **Auto-Activation**: Intelligent routing based on context and keywords
- **Multi-Agent Coordination**: Parallel and sequential agent orchestration
- **Quality Gates**: Built-in validation and quality assurance

## Agent Architecture

### Agent Types Available in Claude Code Task Tool
- **general-purpose**: Multi-domain research and complex tasks
- **frontend-specialist**: UI/UX development with React, Vue, accessibility
- **backend-specialist**: APIs, databases, server architecture, security
- **qa-specialist**: Testing, quality assurance, performance validation
- **devops-specialist**: CI/CD, infrastructure, deployment, monitoring
- **coordinator**: Multi-agent orchestration and workflow management

## WD Agent Specializations

### `wd-frontend-agent`
**Subagent Type**: `frontend-specialist`
**Domain**: UI/UX Development

**Auto-Activation Triggers**:
- Keywords: component, UI, React, Vue, responsive, accessibility, design-system
- File patterns: `*.jsx`, `*.tsx`, `*.vue`, `*.css`, `*.scss`
- Commands: `/wd:build`, `/wd:design`, `/wd:implement` (frontend context)

**MCP Server Integration**:
- **Primary**: Magic - UI component generation and design systems
- **Secondary**: Context7 - Framework documentation and patterns
- **Tertiary**: Playwright - User interaction testing

**Specialized Capabilities**:
- Modern UI component creation with framework best practices
- Accessibility compliance (WCAG 2.1 AA)
- Responsive design and mobile-first development
- Design system integration and token management
- Performance optimization (Core Web Vitals)

### `wd-backend-agent`
**Subagent Type**: `backend-specialist`
**Domain**: Server-Side Development

**Auto-Activation Triggers**:
- Keywords: API, database, server, endpoint, authentication, microservices
- File patterns: `*.js`, `*.ts`, `*.py`, `*.go`, `controllers/*`, `models/*`
- Commands: `/wd:implement` (backend context), `/wd:security`, `/wd:performance`

**MCP Server Integration**:
- **Primary**: Context7 - Framework documentation and server patterns
- **Secondary**: Sequential - Complex backend logic and architecture
- **Tertiary**: Playwright - API testing and validation

**Specialized Capabilities**:
- RESTful and GraphQL API design and implementation
- Database optimization and query performance
- Authentication and authorization systems
- Microservices architecture and communication
- Security best practices and vulnerability assessment

### `wd-security-agent`
**Subagent Type**: `qa-specialist` (security focus)
**Domain**: Security Analysis

**Auto-Activation Triggers**:
- Keywords: security, vulnerability, authentication, authorization, audit
- File patterns: `*auth*`, `*security*`, `*.pem`, `*.key`
- Commands: `/wd:review --focus security`, `/wd:analyze`, `/wd:audit`

**MCP Server Integration**:
- **Primary**: Sequential - Systematic security analysis
- **Secondary**: Context7 - Security patterns and compliance standards
- **Tertiary**: Playwright - Security testing and penetration testing

**Specialized Capabilities**:
- Vulnerability assessment and threat modeling
- Security code review and static analysis
- Compliance validation (OWASP, SOC2, GDPR)
- Authentication and authorization auditing
- Secure development practices enforcement

### `wd-test-agent`
**Subagent Type**: `qa-specialist`
**Domain**: Quality Assurance & Testing

**Auto-Activation Triggers**:
- Keywords: test, testing, E2E, unit, integration, coverage, quality
- File patterns: `*.test.*`, `*.spec.*`, `__tests__/*`, `cypress/*`, `playwright/*`
- Commands: `/wd:test`, `/wd:benchmark`, `/wd:review --focus quality`

**MCP Server Integration**:
- **Primary**: Playwright - E2E testing and browser automation
- **Secondary**: Sequential - Test strategy and coverage analysis
- **Tertiary**: Context7 - Testing patterns and best practices

**Specialized Capabilities**:
- Comprehensive test strategy development
- E2E test automation with cross-browser compatibility
- Performance testing and benchmarking
- Test coverage analysis and improvement
- Quality metrics and reporting

### `wd-docs-agent`
**Subagent Type**: `general-purpose` (documentation focus)
**Domain**: Documentation & Knowledge Management

**Auto-Activation Triggers**:
- Keywords: document, README, wiki, guide, manual, docs, changelog
- File patterns: `*.md`, `*.rst`, `docs/*`, `README*`
- Commands: `/wd:document`, `/wd:explain`, `/wd:finalize` (documentation phase)

**MCP Server Integration**:
- **Primary**: Context7 - Documentation patterns and style guides
- **Secondary**: Sequential - Structured content organization
- **Tertiary**: Magic - Interactive documentation components

**Specialized Capabilities**:
- Technical documentation creation and maintenance
- API documentation generation and validation
- Multi-language documentation and localization
- Documentation site generation and deployment
- Knowledge base organization and search optimization

## Agent Activation System

### Manual Activation
Use command flags to explicitly activate agents:
```bash
/wd:implement --agent wd-frontend-agent
/wd:review --agent wd-security-agent
/wd:test --agent wd-test-agent
```

### Auto-Activation Matrix
```yaml
activation_scoring:
  keyword_match: 40%      # Domain-specific keywords
  file_context: 30%       # File patterns and project structure
  command_context: 20%    # Command type and arguments
  complexity_level: 10%   # Task complexity assessment

thresholds:
  auto_activate: 70%      # Automatically activate agent
  suggest_agent: 50%      # Suggest agent activation
  multi_agent: 85%        # Activate multiple coordinated agents
```

### Multi-Agent Coordination Patterns

#### Parallel Delegation
```yaml
pattern: parallel_agents
use_case: "Independent domain analysis"
example: "/wd:review --comprehensive"
agents: [wd-frontend-agent, wd-backend-agent, wd-security-agent]
coordination: "Parallel execution with result aggregation"
```

#### Sequential Workflow
```yaml
pattern: sequential_agents
use_case: "Dependent task pipeline"
example: "/wd:implement → /wd:test → /wd:document"
agents: [wd-backend-agent → wd-test-agent → wd-docs-agent]
coordination: "Sequential handoff with context preservation"
```

#### Hierarchical Orchestration
```yaml
pattern: hierarchical_coordination
use_case: "Complex multi-domain projects"
example: "/wd:migrate React Vue --comprehensive"
coordinator: "coordinator subagent"
specialists: [wd-frontend-agent, wd-test-agent, wd-docs-agent]
coordination: "Central coordinator with specialist delegation"
```

## Agent Integration with Commands

### Wave-Enabled Commands with Agents
- **`/wd:review`**: Multi-agent parallel analysis (security, performance, quality)
- **`/wd:migrate`**: Coordinated migration with frontend, backend, and testing
- **`/wd:implement`**: Domain-specific implementation with appropriate specialist
- **`/wd:brainstorm`**: Multi-perspective ideation with diverse agents

### Agent-Command Optimization Matrix
| Command | Primary Agent | Secondary Agents | Coordination Pattern |
|---------|---------------|------------------|---------------------|
| `/wd:implement` | Domain-specific | test-agent | Sequential |
| `/wd:review` | qa-specialist | security, performance | Parallel |
| `/wd:migrate` | frontend/backend | test-agent, docs-agent | Hierarchical |
| `/wd:finalize` | docs-agent | security-agent | Sequential |
| `/wd:benchmark` | test-agent | performance, frontend | Parallel |

## Quality Gates & Validation

### Agent Quality Standards
- **Completion Criteria**: Clear deliverables and success metrics
- **Inter-Agent Communication**: Structured handoff protocols
- **Result Validation**: Quality checks and compatibility verification
- **Error Recovery**: Fallback strategies and graceful degradation

### Performance Monitoring
- **Agent Response Time**: <30s for simple tasks, <5min for complex
- **Success Rate**: >90% completion rate with quality validation
- **Resource Usage**: Optimized token usage and memory management
- **User Satisfaction**: Clear communication and expected outcomes

## Advanced Agent Features

### Context Preservation
- **Session Memory**: Maintain context across agent switches
- **Domain Knowledge**: Persistent learning from successful patterns
- **User Preferences**: Adapt to user coding style and preferences
- **Project Context**: Remember project-specific configurations

### Intelligent Routing
- **Dynamic Selection**: Choose optimal agent based on current context
- **Load Balancing**: Distribute work across available agents
- **Fallback Mechanisms**: Graceful degradation when agents unavailable
- **Performance Optimization**: Route to fastest available specialist

### Learning & Adaptation
- **Pattern Recognition**: Learn from successful agent combinations
- **Performance Feedback**: Improve routing based on outcomes
- **User Feedback Integration**: Adapt to explicit user preferences
- **Continuous Improvement**: Update agent capabilities and coordination

## Usage Examples

### Simple Agent Invocation
```bash
# Explicit frontend agent for component creation
/wd:implement LoginComponent --agent wd-frontend-agent

# Security-focused review
/wd:review auth-system --agent wd-security-agent
```

### Multi-Agent Workflows
```bash
# Comprehensive system review with multiple agents
/wd:review --comprehensive --agents security,performance,quality

# Full-stack feature implementation
/wd:implement user-dashboard --agents frontend,backend,test,docs
```

### Advanced Orchestration
```bash
# Complex migration with hierarchical coordination
/wd:migrate Angular React --strategy comprehensive --agents all
```

## Best Practices

### Agent Selection
1. **Trust Auto-Activation**: The system learns your patterns
2. **Be Specific**: Use detailed descriptions for better agent matching
3. **Combine Appropriately**: Some tasks benefit from multiple perspectives
4. **Monitor Results**: Review agent performance and adjust preferences

### Multi-Agent Coordination
1. **Clear Objectives**: Define expected outcomes for each agent
2. **Manage Dependencies**: Understand sequential vs. parallel workflows
3. **Quality Gates**: Ensure each agent meets quality standards
4. **Communication**: Facilitate clear handoffs between agents

### Performance Optimization
1. **Right-Size Tasks**: Match task complexity to agent capabilities
2. **Avoid Over-Delegation**: Simple tasks don't need agent complexity
3. **Monitor Resource Usage**: Be aware of token and time costs
4. **Learn from Patterns**: Observe successful agent combinations