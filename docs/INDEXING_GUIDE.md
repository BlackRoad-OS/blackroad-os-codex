# 📑 Indexing Guide

How to add new repositories to the BlackRoad Codex index.

---

## Index a Single Repository

```bash
python3 blackroad-codex-scanner.py --repo /path/to/your/repo
```

The scanner will:
1. Recursively walk all source files
2. Parse Python and TypeScript/JavaScript with AST
3. Extract functions, classes, modules, API endpoints, and React components
4. Store everything in the local SQLite database

---

## Index All BlackRoad Repos

```bash
./blackroad-codex-index-all.sh
```

This script discovers and indexes every repo in the BlackRoad ecosystem automatically.

---

## What Gets Indexed?

| Component Type | Language | Example |
|----------------|----------|---------|
| Functions | Python, JS/TS | `def authenticate(user)` |
| Classes | Python, JS/TS | `class UserService` |
| Modules | Python | `import blackroad_auth` |
| API Endpoints | Python (FastAPI/Flask) | `@router.post("/login")` |
| React Components | TypeScript/JSX | `export const Button` |

---

## Verifying the Index

After indexing, check the stats:

```bash
python3 blackroad-codex-scraping-dashboard.py
```

Or query directly:

```bash
sqlite3 ~/blackroad-codex/index/components.db "
  SELECT language, COUNT(*) as count
  FROM components
  GROUP BY language
  ORDER BY count DESC
"
```

---

## Re-indexing

To refresh an already-indexed repo after code changes:

```bash
python3 blackroad-codex-scanner.py --repo /path/to/repo --refresh
```

---

*See [DATABASE_SCHEMA.md](DATABASE_SCHEMA.md) for full schema details.*
