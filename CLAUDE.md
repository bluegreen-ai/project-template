# Project Guidelines for Claude Code

## Communication Language Policy

**IMPORTANT**: The project maintainer is French-speaking, so:
- ✅ **Conversations can be in French** (easier for communication and explanations)
- ⚠️ **All code, documentation, comments, and commit messages MUST be in English**
- ⚠️ **All project files (README, docs/, etc.) MUST be in English**

This ensures the codebase remains accessible to international contributors while allowing comfortable communication with the maintainer.

**Examples:**
- ✅ Chat: "Peux-tu m'expliquer comment ça marche ?"
- ✅ Code: `function calculateTotal() { /* English comments */ }`
- ✅ Commit: "feat: add user authentication"
- ❌ Code: `function calculerTotal() { /* commentaires français */ }`
- ❌ Commit: "ajout: authentification utilisateur"

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

## Archon MCP Server Integration

**IMPORTANT**: This project uses Archon MCP server for knowledge management and task tracking.

### Archon RAG (Knowledge Base)

During planning (`/core_piv_loop:plan-feature`):
- Use `mcp__archon__rag_get_available_sources()` to list available documentation
- Search with `mcp__archon__rag_search_knowledge_base(query="...")` for patterns
- Find code examples with `mcp__archon__rag_search_code_examples(query="...")`

**Tips:**
- Keep queries short (2-5 keywords)
- Search before implementing new features

### Archon Task Management

The execute command automatically:
- Creates project in Archon if project ID specified
- Creates all tasks from plan in Archon
- Tracks task status (todo → doing → review → done)

### Current Project

**Archon Project ID**: [Specify if part of a larger project]

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
