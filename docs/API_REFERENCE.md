# 📘 API Reference

Programmatic access to the BlackRoad Codex.

---

## Python API

### Search

```python
from blackroad_codex_search import CodexSearch

searcher = CodexSearch()
results = searcher.search("authentication jwt")

for r in results:
    print(r.name, r.repo, r.file, r.score)
```

### Scanner

```python
from blackroad_codex_scanner import CodexScanner

scanner = CodexScanner()
components = scanner.scan("/path/to/repo")
print(f"Found {len(components)} components")
```

### Symbolic Engine

```python
from blackroad_codex_symbolic import SymbolicComputationEngine

engine = SymbolicComputationEngine()

# Verify symbolic equivalence
is_equiv = engine.verify_symbolic_equivalence("a * (b + c)", "a*b + a*c")
print(is_equiv)  # True — distributive property

# Generate LaTeX
latex = engine.to_latex("E = m * c**2")
print(latex)  # E = mc^{2}
```

---

## CLI Reference

| Command | Description |
|---------|-------------|
| `python3 blackroad-codex-search.py "query"` | Search components |
| `python3 blackroad-codex-scanner.py --repo <path>` | Index a repo |
| `python3 blackroad-codex-scraping-dashboard.py` | View statistics |
| `./blackroad-codex-verification-suite.sh verify <id> <file>` | Verify a component |
| `./blackroad-codex-verification-suite.sh identities` | List math identities |
| `./blackroad-codex-verification-suite.sh dashboard` | Verification dashboard |
| `./blackroad-codex-index-all.sh` | Index all repos |

---

## Database Schema (Summary)

```sql
-- Core tables
components (id, name, repo, file, type, language, docstring, created_at)
dependencies (component_id, depends_on_id)
documentation (component_id, content)

-- Verification tables
calculations (id, component_id, original, simplified, latex, domain)
math_identities (id, name, lhs, rhs, domain)
verifications (id, component_id, status, details, timestamp)
```

Full schema: [DATABASE_SCHEMA.md](DATABASE_SCHEMA.md)

---

*For the verification framework, see [CODEX_VERIFICATION_GUIDE.md](CODEX_VERIFICATION_GUIDE.md).*
