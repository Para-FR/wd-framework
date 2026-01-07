# Local Installation Test - Phase 4

## Pre-Test Verification ✅

### Plugin Structure (Verified)
```
godev-framework-plugin/
├── .claude-plugin/
│   ├── plugin.json ✅
│   └── marketplace.json ✅
├── commands/ (17 files) ✅
│   ├── gd-analyze.md
│   ├── gd-implement.md
│   ├── gd-build.md
│   └── ... (14 more)
├── agents/ (5 files) ✅
│   ├── gd-frontend-agent.md
│   ├── gd-backend-agent.md
│   ├── gd-security-agent.md
│   ├── gd-test-agent.md
│   └── gd-docs-agent.md
├── .claude/ (15 core files) ✅
│   ├── CLAUDE.md
│   ├── COMMANDS.md
│   ├── PERSONAS.md
│   └── ... (12 more)
└── Documentation ✅
    ├── README.md
    ├── PLUGIN_DEVELOPMENT.md
    └── CHANGELOG.md
```

### Frontmatter Validation ✅
- Commands have proper YAML frontmatter with `allowed-tools`, `description`, `auto-persona`
- Agents have `subagent-type`, `domain`, `auto-activation-keywords`, `file-patterns`

## Test Commands

### Step 1: Add Local Marketplace
```bash
/plugin marketplace add /Users/adev/Documents/GoDev_Framework/godev-framework-plugin
```

**Expected Output:**
```
✅ Marketplace 'godev-framework-plugin' added successfully
```

**Possible Errors:**
- ❌ "Invalid marketplace.json" → Check JSON schema
- ❌ "Path not found" → Verify absolute path

### Step 2: List Marketplaces
```bash
/plugin marketplace list
```

**Expected Output:**
```
Installed Marketplaces:
- godev-framework-plugin
  Owner: Para-FR
  Plugins: 1 (godev-framework)
```

### Step 3: List Available Plugins
```bash
/plugin list
```

**Expected Output:**
```
Available Plugins:
- godev-framework v1.0.0 (from godev-framework-plugin)
  Description: Advanced AI development framework with 11 AI personas, 22 specialized commands...
  Commands: 17
  Agents: 5
```

### Step 4: Install Plugin
```bash
/plugin install godev-framework@godev-framework-plugin
```

**Expected Output:**
```
✅ Installing plugin 'godev-framework' from 'godev-framework-plugin'...
✅ Installed 17 commands
✅ Installed 5 agents
✅ Plugin 'godev-framework' installed successfully
```

### Step 5: Verify Commands Available
```bash
/wd:analyze --help
```

**Expected Output:**
Should display the command help with description and usage.

### Step 6: List Installed Plugins
```bash
/plugin list --installed
```

**Expected Output:**
```
Installed Plugins:
- godev-framework v1.0.0
  Commands: gd-analyze, gd-implement, gd-build, ...
  Agents: gd-frontend-agent, gd-backend-agent, ...
```

## Troubleshooting

### Issue: "Invalid marketplace.json schema"
**Fix:** Verify JSON structure matches Claude Code requirements:
```json
{
  "name": "marketplace-name",
  "owner": { "name": "...", "email": "..." },
  "plugins": [
    {
      "name": "plugin-name",
      "source": ".",
      "version": "1.0.0",
      ...
    }
  ]
}
```

### Issue: "Commands not available after installation"
**Fix:**
1. Check command files have proper frontmatter
2. Verify file names match marketplace.json `commands` list
3. Try `/plugin reload godev-framework`

### Issue: "Agents not activating"
**Fix:**
1. Check agent files have `subagent-type` in frontmatter
2. Verify `auto-activation-keywords` match your context
3. Try explicitly spawning: `/wd:spawn frontend`

## Success Criteria ✅

- [ ] Marketplace added without errors
- [ ] Plugin appears in `/plugin list`
- [ ] Plugin installs successfully
- [ ] All 17 commands available (test with `/wd:analyze --help`)
- [ ] Agents can be spawned (test with `/wd:spawn frontend`)
- [ ] Core framework files loaded (check with context)

## Next Steps

If all tests pass:
→ **Phase 5:** Push to GitHub and test remote installation
→ **Phase 6:** Test GitHub installation with `Para-FR/godev-framework`
→ **Phase 7:** Validate all commands and agents work correctly

If tests fail:
→ Review errors, fix JSON/frontmatter issues, re-test
