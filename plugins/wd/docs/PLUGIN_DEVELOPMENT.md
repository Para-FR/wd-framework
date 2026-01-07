# Plugin Development Guide

Complete guide to creating Claude Code plugins compatible with GoDev Framework ecosystem.

## Table of Contents

1. [Quick Start](#quick-start)
2. [Plugin Structure](#plugin-structure)
3. [Creating Commands](#creating-commands)
4. [Agent Configuration](#agent-configuration)
5. [MCP Integration](#mcp-integration)
6. [Publishing](#publishing)
7. [Best Practices](#best-practices)

## Quick Start

### 30-Minute First Plugin

Create a new plugin in under 30 minutes:

```bash
# 1. Create directory structure
mkdir my-awesome-plugin
cd my-awesome-plugin

# 2. Create minimal structure
mkdir -p .claude-plugin commands agents

# 3. Create marketplace.json
cat > .claude-plugin/marketplace.json <<EOF
{
  "name": "my-awesome-plugin",
  "version": "0.1.0",
  "displayName": "My Awesome Plugin",
  "description": "Your plugin description",
  "author": {
    "name": "Your Name",
    "email": "you@example.com"
  },
  "repository": {
    "type": "git",
    "url": "https://github.com/yourusername/my-awesome-plugin"
  },
  "license": "MIT",
  "components": {
    "commands": "./commands"
  }
}
EOF

# 4. Create your first command
cat > commands/my-command.md <<EOF
---
allowed-tools: [Read, Write, Bash]
description: "Does something awesome"
---

# /my:command

## Purpose
Explain what your command does

## Usage
\`\`\`bash
/my:command [arguments] [--flags]
\`\`\`

## Examples
\`\`\`bash
/my:command input --flag
\`\`\`
EOF

# 5. Initialize git repository
git init
git add .
git commit -m "Initial commit"

# 6. Push to GitHub
git remote add origin https://github.com/yourusername/my-awesome-plugin.git
git push -u origin main

# 7. Install and test
# In Claude Code:
# /plugin marketplace add yourusername/my-awesome-plugin
```

Done! Your plugin is now installable via Claude Code marketplace.

## Plugin Structure

### Minimal Structure

```
my-plugin/
├── .claude-plugin/
│   └── marketplace.json       # Required: Plugin configuration
├── commands/                  # Optional: Slash commands
│   └── my-command.md
├── README.md                 # Recommended: Documentation
└── LICENSE                   # Recommended: License file
```

### Complete Structure

```
my-plugin/
├── .claude-plugin/
│   └── marketplace.json       # Plugin configuration
│
├── commands/                  # Slash commands
│   ├── command1.md
│   ├── command2.md
│   └── command3.md
│
├── agents/                    # Agent configurations
│   ├── my-frontend-agent.md
│   └── my-backend-agent.md
│
├── .claude/                   # Framework core files
│   ├── CORE.md
│   └── RULES.md
│
├── hooks/                     # Hook definitions
│   └── pre-commit.md
│
├── mcp/                       # MCP server configs
│   └── my-server-config.json
│
├── docs/                      # Documentation
│   ├── getting-started.md
│   └── reference.md
│
├── examples/                  # Example usage
│   └── basic-usage.md
│
├── README.md
├── LICENSE
├── CHANGELOG.md
└── .gitignore
```

## Creating Commands

### Command File Format

Commands are markdown files with YAML frontmatter:

```markdown
---
allowed-tools: [Read, Write, Edit, Bash, Glob, Grep, TodoWrite, Task]
description: "Short command description"
category: "Development"
auto-persona: ["architect", "frontend"]
mcp-servers: ["context7", "sequential"]
wave-enabled: true
---

# /my:command - Command Title

## Purpose
Clear description of what the command does and when to use it.

## Usage
\`\`\`bash
/my:command [target] [@<path>] [!<command>] [--<flags>]
\`\`\`

## Arguments
- `[target]` - Description of target argument
- `@<path>` - Optional path specification
- `!<command>` - Optional command to run first
- `--flag` - Optional flag description

## Execution Workflow
1. First step
2. Second step
3. Final step

## Examples
\`\`\`bash
# Example 1: Basic usage
/my:command target

# Example 2: With flags
/my:command target --flag value

# Example 3: Complex usage
/my:command @src/ --depth deep --format json
\`\`\`

## Integration Features
- Tool coordination
- Error handling
- Quality gates

## Related Commands
- `/other:command` - Related functionality
```

### Frontmatter Options

```yaml
---
# Required
allowed-tools: [Read, Write, Bash]  # Tools command can use
description: "Command description"   # Short description

# Optional but recommended
category: "Development|Analysis|Quality|Workflow"
auto-persona: ["architect", "frontend", "backend"]
mcp-servers: ["context7", "sequential", "magic", "playwright"]
wave-enabled: true|false
performance-profile: "optimization|standard|complex"

# Advanced
requires: ["dependency-command"]
conflicts: ["incompatible-command"]
version: "1.0.0"
---
```

### Allowed Tools

Available tools for commands:

- **Read** - Read files
- **Write** - Write new files
- **Edit** - Edit existing files
- **MultiEdit** - Edit multiple files
- **Bash** - Execute shell commands
- **Glob** - File pattern matching
- **Grep** - Content search
- **TodoWrite** - Task management
- **Task** - Sub-agent delegation
- **WebFetch** - Fetch web content
- **WebSearch** - Search web

## Agent Configuration

### Agent File Format

```markdown
---
subagent-type: "frontend-specialist|backend-specialist|qa-specialist|general-purpose|coordinator"
domain: "Specialized Domain"
focus: "specific-focus-area"
auto-activation-keywords: ["keyword1", "keyword2"]
file-patterns: ["*.jsx", "*.tsx"]
commands: ["/wd:implement", "/wd:build"]
mcp-servers: ["magic", "context7"]
---

# Agent Name

## Purpose
What this agent specializes in

## Domain Expertise
- Expertise area 1
- Expertise area 2

## Auto-Activation Triggers
When this agent activates automatically

## MCP Server Integration
How it uses MCP servers

## Specialized Capabilities
What makes this agent unique

## Quality Standards
Standards it enforces

## Common Tasks
Typical use cases

## Best Practices
Guidelines for using this agent
```

## MCP Integration

### MCP Server Configuration

```json
{
  "name": "my-mcp-server",
  "command": "npx",
  "args": ["-y", "@my-scope/my-mcp-server"],
  "env": {
    "API_KEY": "${MY_API_KEY}"
  }
}
```

### Using MCP in Commands

Specify MCP servers in command frontmatter:

```yaml
---
mcp-servers: ["context7", "sequential", "my-custom-server"]
---
```

Commands will automatically coordinate with specified MCP servers.

## Publishing

### 1. Prepare Repository

```bash
# Ensure all files are committed
git add .
git commit -m "Prepare for release"

# Tag release
git tag v1.0.0
git push origin main --tags
```

### 2. Create GitHub Release

1. Go to your repository on GitHub
2. Click "Releases" → "Create a new release"
3. Choose your tag (v1.0.0)
4. Write release notes
5. Publish release

### 3. Update marketplace.json

```json
{
  "version": "1.0.0",
  "changelog": "./CHANGELOG.md"
}
```

### 4. Announce

Share your plugin:
- Claude Code Discord
- GitHub Discussions
- Social media
- Developer forums

## Best Practices

### Command Design

1. **Single Responsibility**
   - One clear purpose per command
   - Avoid feature creep
   - Compose multiple commands for complex workflows

2. **Clear Naming**
   - Descriptive command names
   - Consistent namespace (`/my:` prefix)
   - Avoid conflicts with popular plugins

3. **Good Documentation**
   - Clear purpose statement
   - Comprehensive examples
   - All arguments documented
   - Expected outcomes described

4. **Error Handling**
   - Graceful failure modes
   - Helpful error messages
   - Recovery suggestions
   - Validation before execution

### Performance

1. **Tool Selection**
   - Use minimal set of tools needed
   - Prefer specific tools over general ones
   - Consider token usage

2. **Execution Speed**
   - Avoid unnecessary operations
   - Use caching when appropriate
   - Parallel execution where possible
   - Progress feedback for long operations

### Quality

1. **Testing**
   - Test with various inputs
   - Edge case handling
   - Error scenario testing
   - Integration testing

2. **Security**
   - Input validation
   - Safe command execution
   - No hardcoded secrets
   - Proper error messages (no sensitive info)

3. **Maintenance**
   - Regular updates
   - Dependency updates
   - Bug fixes
   - Feature improvements

### User Experience

1. **Helpful Output**
   - Clear status messages
   - Progress indicators
   - Actionable next steps
   - Links to documentation

2. **Flexibility**
   - Sensible defaults
   - Configurable options
   - Multiple use cases
   - Good flag design

3. **Integration**
   - Works with other plugins
   - Follows conventions
   - Compatible with workflows
   - Complementary features

## Examples

### Simple Plugin (Single Command)

**marketplace.json**:
```json
{
  "name": "hello-plugin",
  "version": "1.0.0",
  "displayName": "Hello Plugin",
  "description": "Simple greeting plugin",
  "components": {
    "commands": "./commands"
  }
}
```

**commands/hello.md**:
```markdown
---
allowed-tools: []
description: "Greet the user"
---

# /hello:world

## Purpose
Simple greeting command

## Usage
\`\`\`bash
/hello:world [name]
\`\`\`

## Examples
\`\`\`bash
/hello:world Alice
# Output: Hello, Alice!
\`\`\`
```

### Multi-Command Plugin

See the [examples/multi-command-plugin](./examples/multi-command-plugin/) directory for a complete example with:
- Multiple commands
- Agent configuration
- MCP integration
- Documentation

## Resources

- [Claude Code Documentation](https://docs.anthropic.com/claude-code)
- [GoDev Framework](https://github.com/godevstudio/godev-framework)
- [Plugin Examples](./examples/)
- [Community Plugins](https://github.com/topics/claude-code-plugin)

## Support

- 💬 [Discord Community](https://discord.gg/godevstudio)
- 🐛 [Issue Tracker](https://github.com/godevstudio/godev-framework/issues)
- 📧 [Email](mailto:support@godev-studio.com)

---

Happy plugin development! 🚀
