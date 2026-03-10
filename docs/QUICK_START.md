# ⚡ Quick Start Tutorial

Welcome! You'll be searching 8,789 components across 56 repos in under 2 minutes.

---

## Step 1 — Install (60 seconds)

```bash
git clone https://github.com/BlackRoad-OS/blackroad-os-codex.git
cd blackroad-os-codex
./setup.sh
```

---

## Step 2 — Your First Search

```bash
python3 blackroad-codex-search.py "authentication login"
```

You'll see a list of matching components with file locations and descriptions.

---

## Step 3 — Try Different Queries

```bash
# Find React UI components
python3 blackroad-codex-search.py "react button modal"

# Find API endpoints
python3 blackroad-codex-search.py "fastapi router endpoint"

# Find math / calculation code
python3 blackroad-codex-search.py "equation matrix calculation"
```

---

## Step 4 — View the Dashboard

```bash
python3 blackroad-codex-scraping-dashboard.py
```

This shows live stats: total components, languages, top repositories, and more.

---

## Step 5 — Index a New Repo

```bash
python3 blackroad-codex-scanner.py --repo /path/to/your/repo
```

After indexing, all of that repo's components appear in search results.

---

## What Next?

| Guide | Link |
|-------|------|
| Deep search techniques | [SEARCH_GUIDE.md](SEARCH_GUIDE.md) |
| Verify math code | [CODEX_VERIFICATION_GUIDE.md](CODEX_VERIFICATION_GUIDE.md) |
| Integrate with Memory | [MEMORY_CODEX_INTEGRATION.md](MEMORY_CODEX_INTEGRATION.md) |
| Full API reference | [API_REFERENCE.md](API_REFERENCE.md) |

---

*You're all set — happy searching! 🔍*
