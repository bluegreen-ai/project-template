# Archon MCP Server (Documentation Search)

## When to Read
Read this when you need to search external documentation or find code examples.

---

## Available Tools

| Tool | Purpose |
|------|---------|
| `rag_get_available_sources` | List available documentation sources |
| `rag_search_knowledge_base` | Search documentation by topic |
| `rag_search_code_examples` | Find code examples |
| `rag_read_full_page` | Get complete page content |
| `rag_list_pages_for_source` | Browse all pages in a source |

---

## Usage Pattern

### 1. Find the Right Source
```
rag_get_available_sources()
→ Returns list with id, title, url
```

### 2. Search with Source Filter
```
rag_search_knowledge_base(
    query="authentication JWT",
    source_id="src_abc123",  # From step 1
    match_count=5
)
```

### 3. Read Full Page if Needed
```
rag_read_full_page(page_id="...")
```

---

## Query Tips

### Keep Queries Short (2-5 keywords)

| Good | Bad |
|------|-----|
| `vector search pgvector` | `how to implement vector search with pgvector in PostgreSQL` |
| `React useState` | `React hooks useState useEffect useContext` |
| `FastAPI middleware` | `how to create middleware in FastAPI for authentication` |

### Search Strategy
1. Start with 2-3 keywords
2. If no results, try synonyms
3. Use `source_id` to narrow scope
4. Do multiple focused queries instead of one broad query

---

## Examples

### Search Supabase Docs
```
# 1. Get sources
rag_get_available_sources()
# Find: {"id": "src_supabase", "title": "Supabase Docs", ...}

# 2. Search
rag_search_knowledge_base(
    query="row level security",
    source_id="src_supabase"
)
```

### Find Code Examples
```
rag_search_code_examples(
    query="FastAPI dependency injection",
    match_count=3
)
```

---

## When to Use

- **Before implementing**: Search for best practices
- **When stuck**: Find examples of similar implementations
- **For unfamiliar tech**: Read official docs first
- **Debugging**: Search for known issues or error messages
