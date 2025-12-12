# Claude Code Project Template 🚀

Template de démarrage complet pour nouveaux projets avec Claude Code. Inclut des workflows éprouvés et des commandes slash puissantes.

## 📦 Contenu

### Fichiers de configuration
- **CLAUDE.md** - Documentation projet pour Claude Code
- **INITIAL.md** - Template pour context engineering
- **INITIAL_EXAMPLE.md** - Exemple d'utilisation du context engineering

### Commandes slash (`.claude/commands/`)

#### 🔄 Workflow de base (simple)
- `/primer` - Charger le contexte du projet
- `/create-plan` - Créer un plan d'implémentation
- `/execute-plan` - Exécuter un plan avec suivi

#### 🎯 Workflow PIV avancé (core_piv_loop)
- `/core_piv_loop:prime` - Analyse approfondie du codebase
- `/core_piv_loop:plan-feature` - Planification détaillée
- `/core_piv_loop:execute` - Exécution avec gestion de tâches

#### ✅ Validation & qualité
- `/validation:code-review` - Review de code technique
- `/validation:code-review-fix` - Corriger les bugs trouvés en review
- `/validation:validate` - Validation end-to-end complète
- `/validation:validate-simple` - Validation rapide
- `/validation:system-review` - Analyse implémentation vs plan
- `/validation:execution-report` - Rapport d'implémentation

#### 🐛 Debug GitHub
- `/github_bug_fix:rca` - Root Cause Analysis d'une issue GitHub
- `/github_bug_fix:implement-fix` - Implémenter le fix depuis la RCA

#### 🛠️ Utilitaires
- `/commit` - Créer un commit Git propre
- `/create-prd` - Créer un Product Requirements Document
- `/end-to-end-feature` - Développement complet autonome

### Agents spécialisés (`.claude/agents/`)
- `codebase-analyst.md` - Analyse de patterns
- `library-researcher.md` - Recherche de bibliothèques
- `validator.md` - Spécialiste testing

---

## 🚀 Utilisation rapide

### Option 1: GitHub Template (Recommandé ⭐)

1. **Sur GitHub, allez dans Settings de ce repo**
2. **Cochez "Template repository"** (si pas déjà fait)
3. **Pour créer un nouveau projet:**
   - Allez sur https://github.com/bluegreen-ai/project-template
   - Cliquez sur **"Use this template"** (bouton vert)
   - Choisissez **"Create a new repository"**
   - Nommez votre nouveau projet
   - Toutes les commandes sont déjà là ! ✨

### Option 2: Clone manuel

```bash
# Cloner le template
git clone https://github.com/bluegreen-ai/project-template.git mon-nouveau-projet

# Se déplacer dans le projet
cd mon-nouveau-projet

# Supprimer l'historique Git du template
rm -rf .git

# Initialiser un nouveau dépôt Git
git init
git add .
git commit -m "Initial commit from template"

# Personnaliser INITIAL.md et CLAUDE.md pour votre projet
```

### Option 3: Alias shell rapide

Ajoutez à votre `~/.zshrc` ou `~/.bashrc`:

```bash
alias new-project='git clone https://github.com/bluegreen-ai/project-template.git'
```

Puis:
```bash
new-project mon-nouveau-projet
cd mon-nouveau-projet
rm -rf .git && git init
```

---

## 📖 Guide des workflows

### Workflow simple (pour débuter)

**Idéal pour:** Projets simples, prototypes rapides

```bash
# 1. Charger le contexte
/primer

# 2. Créer un plan
/create-plan "Ajouter authentification utilisateur"

# 3. Exécuter le plan
/execute-plan

# 4. Valider rapidement
/validation:validate-simple

# 5. Commit
/commit
```

### Workflow PIV avancé (pour projets sérieux)

**Idéal pour:** Projets professionnels, features complexes

```bash
# 1. Analyse approfondie
/core_piv_loop:prime

# 2. Planification détaillée
/core_piv_loop:plan-feature "Implémenter système de cache avec Redis"

# 3. Exécution avec tracking
/core_piv_loop:execute

# 4. Review de code
/validation:code-review

# 5. Corriger si nécessaire
/validation:code-review-fix

# 6. Validation complète
/validation:validate

# 7. Commit propre
/commit
```

### Workflow Bug Fix GitHub

**Idéal pour:** Résoudre des issues GitHub

```bash
# 1. Analyser la root cause (depuis l'issue #42)
/github_bug_fix:rca 42

# 2. Implémenter le fix
/github_bug_fix:implement-fix 42

# 3. Valider
/validation:validate-simple

# 4. Commit
/commit
```

### Workflow Feature complète (autonome)

**Idéal pour:** Features auto-suffisantes

```bash
# Tout en une seule commande !
/end-to-end-feature "Ajouter export CSV des données utilisateurs"

# Cette commande fait automatiquement:
# - Prime
# - Plan
# - Execute
# - Validate
# - Commit
```

---

## 🎯 Cas d'usage par commande

### Commandes de base

| Commande | Quand l'utiliser | Exemple |
|----------|------------------|---------|
| `/primer` | Au début d'un projet | Comprendre la structure existante |
| `/create-plan` | Avant d'implémenter | Planifier une nouvelle feature |
| `/execute-plan` | Après avoir un plan | Implémenter le plan créé |

### Commandes PIV (avancées)

| Commande | Quand l'utiliser | Exemple |
|----------|------------------|---------|
| `/core_piv_loop:prime` | Analyse détaillée nécessaire | Rejoindre un projet complexe |
| `/core_piv_loop:plan-feature` | Feature complexe | Système d'auth, API REST, etc. |
| `/core_piv_loop:execute` | Implémentation suivie | Features avec multiple étapes |

### Commandes de validation

| Commande | Quand l'utiliser | Exemple |
|----------|------------------|---------|
| `/validation:code-review` | Avant de commit | Review qualité/sécurité |
| `/validation:code-review-fix` | Après review | Corriger les problèmes trouvés |
| `/validation:validate` | Validation E2E | Tester toute la feature |
| `/validation:validate-simple` | Check rapide | Vérification basique |

### Commandes GitHub

| Commande | Quand l'utiliser | Exemple |
|----------|------------------|---------|
| `/github_bug_fix:rca` | Bug complexe | Analyser pourquoi ça crash |
| `/github_bug_fix:implement-fix` | Après RCA | Implémenter la solution |

### Commandes utilitaires

| Commande | Quand l'utiliser | Exemple |
|----------|------------------|---------|
| `/commit` | Créer un commit propre | Après validation réussie |
| `/create-prd` | Documenter une feature | Avant de commencer |
| `/end-to-end-feature` | Feature auto-suffisante | Petite feature indépendante |

---

## 🔧 Configuration post-clone

### 1. Personnaliser les fichiers

```bash
# Éditez INITIAL.md avec le contexte de votre projet
# Éditez CLAUDE.md avec les règles spécifiques

# Optionnel: créer .claude/settings.local.json
# (pour configuration locale non versionnée)
```

### 2. Tester les commandes

```bash
# Dans Claude Code, essayez:
/primer
/validation:code-review
/commit
```

### 3. Ajouter vos propres commandes

```bash
# Créez de nouvelles commandes dans .claude/commands/
# Exemple: .claude/commands/deploy.md

# Utilisez-les avec /deploy
```

---

## 📝 Créer vos propres commandes

Les commandes sont de simples fichiers Markdown avec des variables :

```markdown
<!-- .claude/commands/ma-commande.md -->

Vous êtes un expert en $1.

Analysez le code et proposez des améliorations pour: $ARGUMENTS

Focus sur les best practices.
```

**Variables disponibles:**
- `$1`, `$2`, `$3` - Arguments positionnels
- `$ARGUMENTS` - Tous les arguments comme une chaîne
- `$PLAN` - Plan de la session précédente (si existe)

**Utilisation:**
```bash
/ma-commande "React" "hooks" "performance"
# $1 = "React"
# $2 = "hooks"
# $3 = "performance"
# $ARGUMENTS = "React hooks performance"
```

---

## 🎓 Best Practices

### 1. Commencer simple
- Utilisez d'abord le workflow de base (`/primer`, `/create-plan`, `/execute-plan`)
- Passez au PIV workflow quand vous êtes à l'aise

### 2. Toujours valider
- Utilisez `/validation:code-review` avant de commit
- Utilisez `/validation:validate` pour les features critiques

### 3. Documenter
- Utilisez `/create-prd` pour les features importantes
- Gardez CLAUDE.md à jour avec les règles projet

### 4. Commit proprement
- Utilisez toujours `/commit` pour créer des commits clairs
- Laissez Claude générer les messages de commit

### 5. Personnaliser
- Créez vos propres commandes pour votre workflow
- Adaptez les commandes existantes si besoin

---

## 🔗 Ressources

- [Documentation Claude Code](https://docs.anthropic.com/claude/docs/claude-code)
- [Archon Workflow Example](https://github.com/coleam00/Archon/tree/main/use-cases/archon-example-workflow)
- [Context Engineering Intro](https://github.com/coleam00/context-engineering-intro)

---

## 📄 Licence

Libre d'utilisation pour vos projets.

---

## 🆘 Support

Des questions ? Ouvrez une issue sur le repo !

**Happy coding with Claude! 🤖✨**
