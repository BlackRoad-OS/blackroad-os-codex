# 🔍 Advanced Search Techniques

Go beyond basic keyword search with these power-user tips.

---

## Combine Multiple Keywords

```bash
python3 blackroad-codex-search.py "jwt token refresh oauth"
```

The more relevant keywords you add, the better the ranking.

---

## Search by Component Type

Include the type in your query:

```bash
python3 blackroad-codex-search.py "class UserService"
python3 blackroad-codex-search.py "function calculate_total"
python3 blackroad-codex-search.py "react component navbar"
python3 blackroad-codex-search.py "fastapi endpoint /api/v1"
```

---

## Search by Repository

```bash
python3 blackroad-codex-search.py "blackroad-simple-launch router"
```

---

## Direct SQL Queries

For precise filtering, query the SQLite database directly:

```bash
# Find all functions in a specific repo
sqlite3 ~/blackroad-codex/index/components.db "
  SELECT name, file FROM components
  WHERE repo = 'blackroad-os-api' AND type = 'function'
  LIMIT 20
"

# Full-text search on docstrings
sqlite3 ~/blackroad-codex/index/components.db "
  SELECT name, repo FROM components
  WHERE docstring LIKE '%authentication%'
"
```

---

## Avoid Rebuilding Existing Code

Before writing new code, always search first:

```bash
python3 blackroad-codex-search.py "email notification send"
# If results appear → REUSE the existing code instead of rebuilding!
```

---

*See [CLI_REFERENCE.md](../CLI_REFERENCE.md) for all available commands.*
