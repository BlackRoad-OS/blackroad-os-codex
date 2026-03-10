# 💻 CLI Commands Reference

All command-line tools in the BlackRoad Codex, with usage examples.

---

## `blackroad-codex-search.py`

Semantic code search across all indexed repos.

```bash
python3 blackroad-codex-search.py "query"
```

**Examples:**
```bash
python3 blackroad-codex-search.py "user authentication"
python3 blackroad-codex-search.py "react button component"
python3 blackroad-codex-search.py "matrix multiplication"
```

---

## `blackroad-codex-scanner.py`

Extracts and indexes components from a repository.

```bash
python3 blackroad-codex-scanner.py --repo <path>
python3 blackroad-codex-scanner.py --repo <path> --refresh
```

---

## `blackroad-codex-scraping-dashboard.py`

Displays live statistics dashboard in the terminal.

```bash
python3 blackroad-codex-scraping-dashboard.py
```

---

## `blackroad-codex-verification-suite.sh`

Unified formal verification CLI.

```bash
# Verify a specific component
./blackroad-codex-verification-suite.sh verify <component_id> <file_path>

# List all 76 built-in math identities
./blackroad-codex-verification-suite.sh identities

# Analyze all math-related components
./blackroad-codex-verification-suite.sh analyze-all-math

# Show verification dashboard
./blackroad-codex-verification-suite.sh dashboard
```

---

## `blackroad-codex-index-all.sh`

Indexes all repos in the BlackRoad ecosystem automatically.

```bash
./blackroad-codex-index-all.sh
```

---

## `blackroad-codex-advanced-scraper.py`

Deep documentation scraper for individual components.

```bash
python3 blackroad-codex-advanced-scraper.py --deep-scrape <component_id>
```

---

## `blackroad-codex-prism-analysis.sh`

Prism Console analyzer for advanced reporting.

```bash
./blackroad-codex-prism-analysis.sh dashboard
./blackroad-codex-prism-analysis.sh report <component_id>
```

---

## `setup.sh`

First-time environment setup.

```bash
./setup.sh
```

---

*See [API_REFERENCE.md](API_REFERENCE.md) for the Python library API.*
