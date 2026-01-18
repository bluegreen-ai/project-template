# Claude Code Project Template 🚀

Complete starter template for new projects with Claude Code. Includes battle-tested workflows and powerful slash commands.

## 📦 Contents

### Configuration Files
- **CLAUDE.md** - Global rules and conventions (keep lightweight!)
- **INITIAL.md** - Template for context engineering
- **INITIAL_EXAMPLE.md** - Context engineering usage example

### Documentation Structure (`.claude/`)
- **PRD.md** - Product Requirements Document (the "north star")
- **STATUS.md** - Current sprint, priorities, next actions
- **reference/** - Task-specific patterns (frontend, backend, etc.)

### Slash Commands (`.claude/commands/`)

#### 🔄 Basic Workflow (simple)
- `/primer` - Load project context
- `/create-plan` - Create implementation plan
- `/execute-plan` - Execute plan with tracking

#### 🎯 Advanced PIV Workflow (core_piv_loop)
- `/core_piv_loop:prime` - Deep codebase analysis
- `/core_piv_loop:plan-feature` - Detailed planning
- `/core_piv_loop:execute` - Execution with task management

#### ✅ Validation & Quality
- `/validation:code-review` - Technical code review
- `/validation:code-review-fix` - Fix bugs found in review
- `/validation:validate` - Complete end-to-end validation
- `/validation:validate-simple` - Quick validation
- `/validation:system-review` - Implementation vs plan analysis
- `/validation:execution-report` - Implementation report

#### 🐛 GitHub Debugging
- `/github_bug_fix:rca` - Root Cause Analysis of GitHub issue
- `/github_bug_fix:implement-fix` - Implement fix from RCA

#### 🛠️ Utilities
- `/commit` - Create clean Git commit
- `/create-prd` - Create Product Requirements Document
- `/end-to-end-feature` - Autonomous complete development

### Specialized Agents (`.claude/agents/`)
- `codebase-analyst.md` - Pattern analysis
- `library-researcher.md` - Library research
- `validator.md` - Testing specialist

---

## 🚀 Quick Start

### Option 1: GitHub Template (Recommended ⭐)

1. **Go to Settings of this repo on GitHub**
2. **Check "Template repository"** (if not already done)
3. **To create a new project:**
   - Go to https://github.com/bluegreen-ai/project-template
   - Click **"Use this template"** (green button)
   - Choose **"Create a new repository"**
   - Name your new project
   - All commands are already there! ✨

### Option 2: Manual Clone

```bash
# Clone the template
git clone https://github.com/bluegreen-ai/project-template.git my-new-project

# Navigate to the project
cd my-new-project

# Remove template Git history
rm -rf .git

# Initialize new Git repository
git init
git add .
git commit -m "Initial commit from template"

# Customize INITIAL.md and CLAUDE.md for your project
```

### Option 3: Quick Shell Alias

Add to your `~/.zshrc` or `~/.bashrc`:

```bash
alias new-project='git clone https://github.com/bluegreen-ai/project-template.git'
```

Then:
```bash
new-project my-new-project
cd my-new-project
rm -rf .git && git init
```

---

## 🎯 Core Methodology: PRD-First Development

This template implements the **PRD-First Development** methodology, inspired by [Cole Medin's agentic engineering techniques](https://www.youtube.com/watch?v=ttdWPDmBN_4).

### The 5 Key Techniques

| Technique | Implementation |
|-----------|----------------|
| **1. PRD-First** | `.claude/PRD.md` is your north star - defines entire scope |
| **2. Modular Rules** | `CLAUDE.md` stays light, details in `.claude/reference/` |
| **3. Command-ify Everything** | All workflows are reusable commands |
| **4. Context Reset** | `/clear` between planning and execution |
| **5. System Evolution** | `/validation:system-review` improves the process |

### Documentation Structure

```
.claude/
├── PRD.md           # North star - scope, features, architecture
├── STATUS.md        # Current sprint, priorities, next actions
├── reference/       # Task-specific patterns (loaded only when needed)
│   ├── frontend-patterns.md
│   ├── backend-patterns.md
│   └── testing-patterns.md
└── commands/        # Reusable workflows
```

### The Context Reset Pattern

**Critical**: Always reset context between planning and execution!

```bash
# 1. Prime and plan
/core_piv_loop:prime
# → Reads PRD, STATUS, understands codebase
# → Ask "what should we build next?"

/core_piv_loop:plan-feature "My feature"
# → Creates detailed plan in .agents/plans/

# 2. CONTEXT RESET
/clear  # ← This is crucial!

# 3. Execute with clean context
/core_piv_loop:execute .agents/plans/my-feature.md
# → Executes with only the plan as context
```

**Why?** Planning loads lots of codebase context. Execution needs a clean context window to reason about implementation. The plan document contains everything needed.

---

## 📖 Workflow Guides

### Simple Workflow (for beginners)

**Ideal for:** Simple projects, rapid prototypes

```bash
# 1. Load context
/primer

# 2. Create a plan
/create-plan "Add user authentication"

# 3. Execute the plan
/execute-plan

# 4. Quick validation
/validation:validate-simple

# 5. Commit
/commit
```

### Advanced PIV Workflow (for serious projects)

**Ideal for:** Professional projects, complex features

```bash
# 1. Deep analysis
/core_piv_loop:prime

# 2. Detailed planning
/core_piv_loop:plan-feature "Implement caching system with Redis"

# 3. Execution with tracking
/core_piv_loop:execute

# 4. Code review
/validation:code-review

# 5. Fix if necessary
/validation:code-review-fix

# 6. Complete validation
/validation:validate

# 7. Clean commit
/commit
```

### GitHub Bug Fix Workflow

**Ideal for:** Resolving GitHub issues

```bash
# 1. Analyze root cause (from issue #42)
/github_bug_fix:rca 42

# 2. Implement the fix
/github_bug_fix:implement-fix 42

# 3. Validate
/validation:validate-simple

# 4. Commit
/commit
```

### Complete Feature Workflow (autonomous)

**Ideal for:** Self-contained features

```bash
# Everything in one command!
/end-to-end-feature "Add CSV export of user data"

# This command automatically does:
# - Prime
# - Plan
# - Execute
# - Validate
# - Commit
```

---

## 🎯 Command Use Cases

### Basic Commands

| Command | When to Use | Example |
|---------|-------------|---------|
| `/primer` | Start of project | Understand existing structure |
| `/create-plan` | Before implementing | Plan a new feature |
| `/execute-plan` | After having a plan | Implement created plan |

### PIV Commands (advanced)

| Command | When to Use | Example |
|---------|-------------|---------|
| `/core_piv_loop:prime` | Detailed analysis needed | Join a complex project |
| `/core_piv_loop:plan-feature` | Complex feature | Auth system, REST API, etc. |
| `/core_piv_loop:execute` | Tracked implementation | Multi-step features |

### Validation Commands

| Command | When to Use | Example |
|---------|-------------|---------|
| `/validation:code-review` | Before commit | Quality/security review |
| `/validation:code-review-fix` | After review | Fix found issues |
| `/validation:validate` | E2E validation | Test entire feature |
| `/validation:validate-simple` | Quick check | Basic verification |

### GitHub Commands

| Command | When to Use | Example |
|---------|-------------|---------|
| `/github_bug_fix:rca` | Complex bug | Analyze why it crashes |
| `/github_bug_fix:implement-fix` | After RCA | Implement the solution |

### Utility Commands

| Command | When to Use | Example |
|---------|-------------|---------|
| `/commit` | Create clean commit | After successful validation |
| `/create-prd` | Document a feature | Before starting |
| `/end-to-end-feature` | Self-contained feature | Small independent feature |

---

## 🔧 Post-Clone Configuration

### 1. Customize Files

```bash
# Edit INITIAL.md with your project context
# Edit CLAUDE.md with specific rules

# Optional: create .claude/settings.local.json
# (for local non-versioned configuration)
```

### 2. Test Commands

```bash
# In Claude Code, try:
/primer
/validation:code-review
/commit
```

### 3. Add Your Own Commands

```bash
# Create new commands in .claude/commands/
# Example: .claude/commands/deploy.md

# Use them with /deploy
```

---

## 📝 Creating Your Own Commands

Commands are simple Markdown files with variables:

```markdown
<!-- .claude/commands/my-command.md -->

You are an expert in $1.

Analyze the code and propose improvements for: $ARGUMENTS

Focus on best practices.
```

**Available Variables:**
- `$1`, `$2`, `$3` - Positional arguments
- `$ARGUMENTS` - All arguments as a string
- `$PLAN` - Previous session plan (if exists)

**Usage:**
```bash
/my-command "React" "hooks" "performance"
# $1 = "React"
# $2 = "hooks"
# $3 = "performance"
# $ARGUMENTS = "React hooks performance"
```

---

## 🎓 Best Practices

### 1. Start Simple
- Use basic workflow first (`/primer`, `/create-plan`, `/execute-plan`)
- Move to PIV workflow when comfortable

### 2. Always Validate
- Use `/validation:code-review` before committing
- Use `/validation:validate` for critical features

### 3. Document
- Use `/create-prd` for important features
- Keep CLAUDE.md up to date with project rules

### 4. Commit Cleanly
- Always use `/commit` to create clear commits
- Let Claude generate commit messages

### 5. Customize
- Create your own commands for your workflow
- Adapt existing commands if needed

---

## 🔗 Resources

- [Claude Code Documentation](https://docs.anthropic.com/claude/docs/claude-code)
- [Archon Workflow Example](https://github.com/coleam00/Archon/tree/main/use-cases/archon-example-workflow)
- [Context Engineering Intro](https://github.com/coleam00/context-engineering-intro)

---

## 📄 License

Free to use for your projects.

---

## 🆘 Support

Questions? Open an issue on the repo!

**Happy coding with Claude! 🤖✨**
