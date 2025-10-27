# Project Template

Template de démarrage pour nouveaux projets avec Claude Code et Archon.

## Contenu

Ce template inclut:

- **CLAUDE.md** - Documentation projet pour Claude Code
- **INITIAL.md** - Template pour context engineering
- **INITIAL_EXAMPLE.md** - Exemple d'utilisation du context engineering
- **.claude/** - Configuration Claude Code
  - **commands/** - Commandes slash personnalisées
    - `create-plan.md` - Créer un plan d'implémentation
    - `execute-plan.md` - Exécuter un plan avec suivi
    - `primer.md` - Charger le contexte du projet
    - **archon/** - Commandes Archon spécifiques
    - **prp-any-agent/** - PRP pour agents génériques
    - **prp-claude-code/** - PRP pour Claude Code
  - **agents/** - Agents spécialisés
    - `codebase-analyst.md` - Analyse de patterns
    - `library-researcher.md` - Recherche de bibliothèques
    - `validator.md` - Spécialiste testing

## Utilisation

### Option 1: Clone simple

```bash
# Cloner le template
git clone https://github.com/votreusername/project-template.git mon-nouveau-projet

# Se déplacer dans le projet
cd mon-nouveau-projet

# Supprimer l'historique Git du template
rm -rf .git

# Initialiser un nouveau dépôt Git
git init

# Personnaliser INITIAL.md et CLAUDE.md pour votre projet
```

### Option 2: GitHub Template Repository

1. Sur GitHub, allez dans Settings du repo
2. Cochez "Template repository"
3. Pour créer un nouveau projet:
   - Cliquez sur "Use this template"
   - Choisissez "Create a new repository"
   - Nommez votre nouveau projet

### Option 3: Script rapide

Créez un alias dans votre `~/.zshrc` ou `~/.bashrc`:

```bash
alias new-project='git clone https://github.com/votreusername/project-template.git'
```

Puis:
```bash
new-project mon-nouveau-projet
cd mon-nouveau-projet
rm -rf .git && git init
```

## Configuration post-clone

1. **Personnaliser INITIAL.md** - Ajoutez le contexte de votre projet
2. **Personnaliser CLAUDE.md** - Décrivez votre projet
3. **Ajuster .claude/settings.local.json** - Configuration locale (non versionné)
4. **Tester les commandes** - `/primer`, `/create-plan`, `/execute-plan`

## Commandes disponibles

- `/primer` - Charge le contexte du projet
- `/create-plan` - Transforme des requirements en plan d'implémentation
- `/execute-plan` - Exécute un plan avec suivi des tâches
- Voir `.claude/commands/` pour toutes les commandes

## Sources

- [Archon Example Workflow](https://github.com/coleam00/Archon/tree/main/use-cases/archon-example-workflow)
- [Context Engineering Intro](https://github.com/coleam00/context-engineering-intro)

## Licence

Libre d'utilisation pour vos projets.
