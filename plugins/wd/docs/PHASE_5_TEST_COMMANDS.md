# Phase 5: Test d'Installation Locale - À EXÉCUTER MAINTENANT

## ✅ Pré-requis Validés

- [x] Structure du plugin vérifiée (17 commands, 5 agents, 14 core files)
- [x] plugin.json valide et complet
- [x] marketplace.json valide avec owner et plugins
- [x] Frontmatter YAML présent dans tous les fichiers
- [x] Script de validation passé avec succès

## 🚀 Commandes à Exécuter (Dans Claude Code)

### Étape 1: Ajouter le Marketplace Local
```bash
/plugin marketplace add /Users/adev/Documents/GoDev_Framework/godev-framework-plugin
```

**Résultat Attendu:**
```
✅ Marketplace 'godev-framework-marketplace' added successfully
```

---

### Étape 2: Vérifier que le Marketplace est Listé
```bash
/plugin marketplace list
```

**Résultat Attendu:**
```
Installed Marketplaces:
- godev-framework-marketplace
  Owner: Para-FR
  Plugins: 1
```

---

### Étape 3: Lister les Plugins Disponibles
```bash
/plugin list
```

**Résultat Attendu:**
```
Available Plugins:
- godev-framework v1.0.0 (from godev-framework-marketplace)
  Description: Advanced AI development framework with 11 AI personas...
  Commands: 17
  Agents: 5
```

---

### Étape 4: Installer le Plugin
```bash
/plugin install godev-framework@godev-framework-marketplace
```

**Résultat Attendu:**
```
✅ Installing plugin 'godev-framework' from 'godev-framework-marketplace'...
✅ Installed 17 commands
✅ Installed 5 agents
✅ Plugin 'godev-framework' installed successfully
```

---

### Étape 5: Vérifier qu'une Commande Fonctionne
```bash
/wd:analyze --help
```

**Résultat Attendu:**
Affichage de l'aide de la commande avec description, usage, arguments, etc.

---

### Étape 6: Tester un Agent
```bash
/wd:spawn frontend
```

**Résultat Attendu:**
```
✅ Spawned gd-frontend-agent
Agent specialized in: UI/UX Development
```

---

### Étape 7: Lister les Plugins Installés
```bash
/plugin list --installed
```

**Résultat Attendu:**
```
Installed Plugins:
- godev-framework v1.0.0
  Commands: gd-analyze, gd-implement, gd-build, gd-improve, gd-test, ...
  Agents: gd-frontend-agent, gd-backend-agent, gd-security-agent, ...
```

---

## 📊 Résumé de Test

### Test Réussi ✅
Si toutes les étapes passent:
- Le plugin s'installe correctement en local
- Les commandes sont disponibles
- Les agents peuvent être activés
- La structure JSON est conforme aux specs Claude Code

**→ Prêt pour Phase 6: Push GitHub et test remote**

### Test Échoué ❌
Si une étape échoue, noter l'erreur exacte:
- Erreur JSON schema → Revoir marketplace.json/plugin.json
- Commandes indisponibles → Vérifier frontmatter YAML
- Agents non reconnus → Vérifier subagent-type

## 🎯 Objectif Phase 5

**Prouver que le plugin fonctionne en installation locale avant de tenter l'installation GitHub.**

Cela permet de:
1. Valider la structure sans dépendance réseau
2. Identifier les problèmes de configuration rapidement
3. S'assurer que le format JSON est correct
4. Confirmer que les commandes et agents sont bien formés

---

**Status actuel:** ⏳ En attente d'exécution des commandes

**Prochain Step:** Exécuter les 7 commandes ci-dessus et reporter le résultat
