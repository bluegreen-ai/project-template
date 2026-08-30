---
paths:
  - "**/supabase/**"
  - "**/migrations/**/*.sql"
  - "**/*.sql"
  - "src/**/*supabase*"
  - "src/**/*Supabase*"
  - "**/supabase.config.*"
  - "**/database.types.ts"
---

# Supabase Conventions

## Two complementary tools — use both

| Need | Tool | Why |
|------|------|-----|
| Browse / read / search docs | **`ssh supabase.sh`** | Bash access to the full docs as markdown — explore freely with `grep`, `find`, `cat`, `head`, `tail` |
| Run operations on the project | **Supabase MCP server** | `apply_migration`, `execute_sql`, `list_tables`, `generate_typescript_types`, `deploy_edge_function`, `get_logs`, `get_advisors`, etc. |

Docs go through SSH. State changes go through MCP. Don't use MCP `search_docs` when SSH bash gives richer exploration.

## Docs via SSH (`ssh supabase.sh`)

All docs live under `/supabase/docs/` as markdown files. Use standard Unix tools.

```bash
# Search for a topic across all docs
ssh supabase.sh grep -rl 'auth' /supabase/docs/

# Read a specific guide
ssh supabase.sh cat /supabase/docs/guides/auth/passwords.md

# Find all guides in a section
ssh supabase.sh find /supabase/docs/guides/database -name '*.md'

# Search with context, scoped to a section
ssh supabase.sh grep -r 'RLS' /supabase/docs/guides/auth --include='*.md' -l

# Skim a long page without bloating context
ssh supabase.sh head -100 /supabase/docs/guides/realtime/postgres-changes.md
```

**Always check the docs before recommending a Supabase API, CLI command, or config option** — the docs are the source of truth, not training data.

## Operations via MCP

For anything that touches the project state:

- Schema changes → `mcp__supabase__apply_migration` (never raw SQL via `execute_sql` for DDL)
- Read-only queries → `mcp__supabase__execute_sql`
- Type generation → `mcp__supabase__generate_typescript_types` after every migration
- Edge functions → `mcp__supabase__deploy_edge_function`
- Debugging → `mcp__supabase__get_logs`, `mcp__supabase__get_advisors`

## Anti-patterns

- Never invent a Supabase API or CLI flag from memory — `ssh supabase.sh grep` first
- Never run DDL through `execute_sql` — use `apply_migration` so it's tracked
- Never commit generated `database.types.ts` without re-running `generate_typescript_types` after a schema change
- Never bypass RLS with the service role key in client-side code
