# 🚀 Installation du Plugin GoDev depuis GitHub

Le plugin a été pushé sur GitHub avec succès! Il est maintenant installable depuis n'importe où.

## 📦 Installation

### Étape 1: Installer depuis GitHub
```bash
/plugin marketplace add Para-FR/godev-framework
```

### Étape 2: Redémarrer Claude Code
**Important:** Fermer complètement Claude Code et le relancer.

### Étape 3: Vérifier l'installation
```bash
/plugin list --installed
```

**Résultat attendu:**
```
Installed Plugins:
- gd v1.0.0 (from gd-marketplace)
  Commands: 17
  Agents: 5
```

## ✅ Test des Commandes

### Commandes Principales
```bash
# Analyse de code
/wd:analyze

# Implémentation de features
/wd:implement

# Build de projet
/wd:build

# Amélioration de code
/wd:improve

# Tests
/wd:test
```

### Toutes les Commandes (17)
- `/wd:analyze` - Multi-dimensional code analysis
- `/wd:implement` - Feature implementation
- `/wd:build` - Project builder with framework detection
- `/wd:improve` - Code quality improvements
- `/wd:test` - Testing and QA
- `/wd:document` - Documentation generation
- `/wd:troubleshoot` - Issue diagnosis
- `/wd:cleanup` - Code cleanup
- `/wd:design` - System design
- `/wd:estimate` - Development estimation
- `/wd:explain` - Code explanation
- `/wd:git` - Git operations
- `/wd:index` - Project indexing
- `/wd:load` - Context loading
- `/wd:spawn` - Task orchestration
- `/wd:task` - Task management
- `/wd:workflow` - Workflow generation

### Agents (5)
- `frontend` - UI/UX development
- `backend` - Server-side development
- `security` - Security analysis
- `test` - QA and testing
- `docs` - Documentation

## 🎯 Format Propre

Les commandes apparaissent maintenant comme:
```
/wd:analyze    Multi-dimensional code and system analysis
               (plugin:gd@gd-marketplace)
```

Au lieu de:
```
/godev-framework:gd-analyze    ...
                              (plugin:godev-framework@godev-framework-marketplace)
```

## 🐛 Troubleshooting

### Erreur SSH
Si vous voyez "SSH authentication failed":
```bash
# Configurer Git pour utiliser HTTPS
git config --global url."https://github.com/".insteadOf git@github.com:

# Réessayer l'installation
/plugin marketplace add Para-FR/godev-framework
```

### Alternative: URL HTTPS Directe
```bash
/plugin marketplace add https://github.com/Para-FR/godev-framework.git
```

### Plugin non visible après installation
1. Vérifier que Claude Code a été redémarré
2. Vérifier avec `/plugin marketplace list`
3. Si nécessaire, retirer et réinstaller:
   ```bash
   /plugin marketplace remove gd-marketplace
   /plugin marketplace add Para-FR/godev-framework
   ```

## 🎉 Succès!

Si tout fonctionne, vous devriez voir:
- ✅ 17 commandes `/wd:*` disponibles
- ✅ 5 agents activables
- ✅ Format propre dans l'autocomplétion
- ✅ Plugin affiché comme `gd@gd-marketplace`

---

**Repository GitHub:** https://github.com/Para-FR/godev-framework
**Commit:** 6361829 (Rename plugin to 'gd' with clean command names)
