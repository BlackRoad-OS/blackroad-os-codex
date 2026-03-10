# 🔍 Search Guide

Everything you need to find code fast across all 56 BlackRoad repositories.

---

## Basic Search

```bash
python3 blackroad-codex-search.py "your query here"
```

The search engine understands natural language — you don't need to know exact function names.

---

## Search Examples

### Find Authentication Code
```bash
python3 blackroad-codex-search.py "authentication jwt login oauth"
```

### Find API Endpoints
```bash
python3 blackroad-codex-search.py "fastapi router endpoint"
```

### Find React Components
```bash
python3 blackroad-codex-search.py "react component button modal"
```

### Find Mathematical Functions
```bash
python3 blackroad-codex-search.py "equation calculation matrix"
```

### Find Database Models
```bash
python3 blackroad-codex-search.py "database model schema"
```

---

## Understanding Results

Each result shows:

| Field | Description |
|-------|-------------|
| **Component ID** | Unique 16-char hash (use for verification) |
| **Name** | Function, class, or module name |
| **Repository** | Which repo it lives in |
| **File** | Path within the repo |
| **Type** | function / class / module / endpoint / component |
| **Score** | Relevance score (higher = better match) |

---

## Tips for Better Searches

- **Use multiple words** — `"user auth token"` beats `"auth"`
- **Use domain terms** — `"fastapi"`, `"react"`, `"sqlite"` narrow results
- **Search by intent** — `"send email notification"` works as well as `"send_email"`

---

## Direct Database Queries

For power users — query the SQLite database directly:

```bash
sqlite3 ~/blackroad-codex/index/components.db "
  SELECT name, repo, file, type
  FROM components
  WHERE name LIKE '%auth%'
  LIMIT 20
"
```

---

*See [API_REFERENCE.md](API_REFERENCE.md) for programmatic access.*
