# 🗄️ Database Schema

The Codex uses SQLite. Default path: `~/blackroad-codex/index/components.db`

---

## Core Tables

### `components`
Stores every indexed code element.

| Column | Type | Description |
|--------|------|-------------|
| `id` | TEXT PRIMARY KEY | 16-char hex hash |
| `name` | TEXT | Function/class/module name |
| `repo` | TEXT | Repository name |
| `file` | TEXT | File path within repo |
| `type` | TEXT | function / class / module / endpoint / component |
| `language` | TEXT | python / typescript / javascript |
| `docstring` | TEXT | Extracted docstring or comment |
| `signature` | TEXT | Full function/class signature |
| `created_at` | TEXT | ISO 8601 timestamp |

### `dependencies`
Component-to-component dependency graph.

| Column | Type | Description |
|--------|------|-------------|
| `component_id` | TEXT | Source component |
| `depends_on_id` | TEXT | Dependency |

### `documentation`
Long-form documentation extracted from components.

| Column | Type | Description |
|--------|------|-------------|
| `component_id` | TEXT | FK → components.id |
| `content` | TEXT | Full documentation text |

---

## Verification Tables

### `calculations`
Mathematical expressions found in code.

| Column | Type | Description |
|--------|------|-------------|
| `id` | TEXT PRIMARY KEY | Hash |
| `component_id` | TEXT | FK → components.id |
| `original` | TEXT | Original expression string |
| `simplified` | TEXT | Simplified form |
| `latex` | TEXT | LaTeX representation |
| `domain` | TEXT | algebra / calculus / linear_algebra / etc. |

### `math_identities`
Built-in mathematical identity database (76 entries).

| Column | Type | Description |
|--------|------|-------------|
| `id` | TEXT PRIMARY KEY | Identity key |
| `name` | TEXT | Human-readable name |
| `lhs` | TEXT | Left-hand side |
| `rhs` | TEXT | Right-hand side |
| `domain` | TEXT | Mathematical domain |

### `verifications`
Results of formal verification runs.

| Column | Type | Description |
|--------|------|-------------|
| `id` | TEXT PRIMARY KEY | Hash |
| `component_id` | TEXT | FK → components.id |
| `status` | TEXT | passed / failed / skipped |
| `details` | TEXT | JSON detail blob |
| `timestamp` | TEXT | ISO 8601 timestamp |

---

## Quick Queries

```bash
# Count by language
sqlite3 ~/blackroad-codex/index/components.db \
  "SELECT language, COUNT(*) FROM components GROUP BY language"

# Top repos by component count
sqlite3 ~/blackroad-codex/index/components.db \
  "SELECT repo, COUNT(*) as n FROM components GROUP BY repo ORDER BY n DESC LIMIT 10"

# Recent verifications
sqlite3 ~/blackroad-codex/index/components.db \
  "SELECT component_id, status, timestamp FROM verifications ORDER BY timestamp DESC LIMIT 10"
```
