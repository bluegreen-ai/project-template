# Project Guidelines for Claude Code

## Communication Language Policy

**IMPORTANT**: The project maintainer is French-speaking, so:
- **Conversations can be in French** (easier for communication and explanations)
- **All code, documentation, comments, and commit messages MUST be in English**
- **All project files (README, docs/, etc.) MUST be in English**

This ensures the codebase remains accessible to international contributors while allowing comfortable communication with the maintainer.

**Examples:**
- Chat: "Peux-tu m'expliquer comment ça marche ?"
- Code: `function calculateTotal() { /* English comments */ }`
- Commit: "feat: add user authentication"

---

## Project Overview

**[Project Name]** - [One sentence description]

**Full specifications**: See `.claude/PRD.md`

---

## Reference Documentation

Read these documents when working on specific areas. This keeps global context light while providing deep knowledge when needed.

| Document | When to Read |
|----------|--------------|
| `.claude/PRD.md` | Understanding project scope, features, architecture |
| `.claude/STATUS.md` | Current sprint priorities, what's done, next actions |
| `.claude/reference/*.md` | Task-specific patterns (frontend, backend, testing, etc.) |

**How to use**: Only read the relevant reference file when working on that specific area. Don't load all files at once.

---

## Tech Stack

- **Language**: [e.g., TypeScript, Python]
- **Framework**: [e.g., Next.js, FastAPI]
- **Database**: [e.g., PostgreSQL, Supabase]
- **Testing**: [e.g., Jest, pytest]

---

## Archon MCP Server (Documentation Search)

Use Archon RAG for documentation search:
- `rag_get_available_sources` - List available documentation sources
- `rag_search_knowledge_base` - Search documentation by topic
- `rag_search_code_examples` - Find code examples

**Tips:**
- Keep queries short (2-5 keywords)
- Use `source_id` to filter by technology
- Search before implementing new features

---

## Task Management (TASKS.md System)

File-based task tracking using markdown files.

**Structure:**
```
.claude/
├── PRD.md              # Vision (stable roadmap)
├── STATUS.md           # Current focus (what you're working on NOW)
└── tasks/              # One file per active feature
    ├── {feature}.md    # Granular tasks for current feature
    └── _archive/       # Completed features
```

**Workflow:**
1. Check `STATUS.md` for current focus and active task file
2. Read the active task file (e.g., `.claude/tasks/auth.md`)
3. Mark task `@claude` when starting: `- [ ] @claude Task description`
4. Mark `[x]` with date when complete: `- [x] Task description ✓ 2026-01-17`
5. When feature complete, move task file to `_archive/`

**Changing Priorities:**
- Update `STATUS.md` to point to new focus
- Create new task file in `.claude/tasks/` if needed

---

## Code Style & Conventions

### Naming
- Files: `kebab-case.ts` / `snake_case.py`
- Classes: `PascalCase`
- Functions: `camelCase` (JS) / `snake_case` (Python)
- Constants: `UPPER_SNAKE_CASE`

### File Organization
```
src/
├── components/    # Reusable components
├── services/      # Business logic
├── utils/         # Helper functions
└── types/         # Type definitions
```

---

## Development Rules

### Type Safety
- Use strict TypeScript (no `any` without justification)
- All functions must have return type annotations

### Testing
- Unit tests required for all new features
- Integration tests for critical flows

### Documentation
- Update README when adding features
- Document complex algorithms

### Git Workflow
- Meaningful commit messages
- No commits with failing tests
- No commits with linting errors

---

## Common Gotchas

[List specific issues Claude should watch for in your project]

- Don't forget to update the schema when adding database fields
- Always use parameterized queries (never string concatenation)
- Check for null before accessing nested properties

---

## External Resources

- [Product Requirements](.claude/PRD.md)
- [Current Status](.claude/STATUS.md)
- [Project README](README.md)
