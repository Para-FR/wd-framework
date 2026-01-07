---
allowed-tools: [Read, Bash, Glob, TodoWrite, Edit, MultiEdit, Task]
description: "Project builder with framework detection and optimization"
wave-enabled: true
category: "Development & Deployment"
auto-persona: ["frontend", "backend", "architect", "devops"]
mcp-servers: ["magic", "context7", "sequential"]
---

# /wd:build - Project Building

## Purpose
Build, compile, and package projects with comprehensive error handling, optimization, and framework-specific intelligence.

## Usage
```bash
/wd:build [target] [--type <type>] [--<flags>]
```

## Arguments
- `[target]` - Project or specific component to build (optional, defaults to current project)
- `--type dev|prod|test|staging` - Build type and environment
- `--clean` - Clean build artifacts before building
- `--optimize` - Enable aggressive build optimizations
- `--verbose` - Enable detailed build output
- `--watch` - Enable watch mode for development
- `--analyze` - Analyze bundle size and dependencies
- `--no-cache` - Disable build cache

## Auto-Activation Patterns

### Personas
- **Frontend**: UI builds with asset optimization
  - Triggers: React, Vue, Angular, Svelte projects
  - Focus: Bundle optimization, code splitting, asset handling

- **Backend**: API and service compilation
  - Triggers: Node.js, Python, Go, Rust projects
  - Focus: Dependency management, environment configs

- **Architect**: Complex multi-service builds
  - Triggers: Monorepos, microservices, multi-target builds
  - Focus: Build orchestration, dependency resolution

- **DevOps**: Production builds and deployment prep
  - Triggers: `--type prod`, CI/CD context
  - Focus: Optimization, security, containerization

### MCP Servers
- **Magic**: UI build optimization and asset processing
- **Context7**: Framework-specific build patterns and best practices
- **Sequential**: Complex multi-step build orchestration

## Framework Detection

### Automatic Detection
- **JavaScript/TypeScript**: package.json scripts detection
- **Python**: setup.py, pyproject.toml, requirements.txt
- **Rust**: Cargo.toml
- **Go**: go.mod
- **Java**: pom.xml, build.gradle
- **C/C++**: CMakeLists.txt, Makefile

### Build Tool Recognition
- npm, yarn, pnpm, bun
- webpack, vite, rollup, esbuild
- cargo, go build
- maven, gradle
- make, cmake

## Execution Workflow

1. **Discovery Phase**
   - Analyze project structure and detect framework
   - Identify build configuration files
   - Determine build tool and commands
   - Check dependencies and environment

2. **Pre-Build Validation**
   - Verify all dependencies are installed
   - Check environment variables
   - Validate build configuration
   - Run type checking (TypeScript, etc.)

3. **Build Execution**
   - Clean artifacts if requested
   - Execute appropriate build commands
   - Monitor build process and capture output
   - Handle errors with diagnostic information

4. **Post-Build Analysis**
   - Analyze build output and artifacts
   - Generate bundle size report (if applicable)
   - Check for common issues
   - Provide optimization recommendations

5. **Quality Gates** (Production Builds)
   - Run tests if available
   - Check bundle size budgets
   - Verify no security vulnerabilities
   - Validate environment configurations

## Examples

```bash
# Development build with watch mode
/wd:build --type dev --watch

# Production build with optimization
/wd:build --type prod --optimize --clean

# Analyze bundle size
/wd:build --type prod --analyze

# Clean build without cache
/wd:build --clean --no-cache

# Build specific target (monorepo)
/wd:build @workspace/frontend --type prod

# Verbose build for debugging
/wd:build --type dev --verbose
```

## Build Optimizations

### Frontend Optimizations
- **Code Splitting**: Automatic route-based splitting
- **Tree Shaking**: Remove unused code
- **Minification**: JavaScript and CSS compression
- **Image Optimization**: Compress and convert images
- **Asset Inlining**: Inline small assets
- **Lazy Loading**: Defer non-critical resources

### Backend Optimizations
- **Dependency Pruning**: Remove dev dependencies
- **Binary Optimization**: Reduce binary size
- **Dead Code Elimination**: Remove unused code paths
- **Compilation Flags**: Optimize for target platform

## Error Handling

### Common Build Errors
1. **Missing Dependencies**
   - Diagnosis: Parse error messages
   - Solution: Auto-suggest installation commands

2. **Type Errors**
   - Diagnosis: Identify type mismatches
   - Solution: Provide fix suggestions

3. **Configuration Issues**
   - Diagnosis: Validate config files
   - Solution: Suggest correct configuration

4. **Memory Issues**
   - Diagnosis: Detect OOM errors
   - Solution: Recommend memory allocation adjustments

### Recovery Strategies
- Automatic retry with cache clearing
- Incremental build fallback
- Dependency reinstallation suggestions
- Configuration validation and fixing

## Output Structure

```markdown
# Build Report: [Project Name]

## Build Configuration
- Type: [dev|prod|test]
- Framework: [framework-name]
- Build Tool: [tool-name]
- Duration: [time]

## Build Steps
✅ Dependency check
✅ Type checking
✅ Compilation
✅ Bundling
✅ Optimization

## Build Artifacts
- Output directory: `./dist`
- Main bundle: `app.js` (245 KB)
- Styles: `app.css` (18 KB)
- Assets: 12 files (1.2 MB)

## Performance Metrics
- Build time: 12.5s
- Bundle size: 245 KB (gzipped: 78 KB)
- Chunks: 8
- Tree shaking: 32% reduction

## Optimization Recommendations
1. Consider code splitting for route `/dashboard`
2. Image `hero.png` can be optimized (save 120 KB)
3. Bundle size exceeds recommended 250 KB threshold

## Next Steps
- Run tests: `/wd:test`
- Deploy build: `/wd:deploy`
- Analyze performance: `/wd:benchmark`
```

## Production Build Checklist

- [ ] Environment variables configured
- [ ] Dependencies up to date
- [ ] Security vulnerabilities checked
- [ ] Tests passing
- [ ] Bundle size within budget
- [ ] Source maps generated
- [ ] Assets optimized
- [ ] Build reproducible
- [ ] Documentation updated

## Related Commands
- `/wd:implement` - Implement new features before building
- `/wd:test` - Run test suite
- `/wd:improve --perf` - Optimize build performance
- `/wd:analyze` - Analyze build configuration
- `/wd:finalize` - Complete build + test + deploy workflow
