# 📂 Indexing Your First Repository

A hands-on tutorial to get your first repo into the Codex.

---

## Before You Start

Make sure you've completed the [Installation Guide](../INSTALLATION.md).

---

## Step 1 — Pick a Repository

Choose any local directory with Python or TypeScript/JavaScript files.

For this tutorial we'll use the Codex itself:

```bash
cd /path/to/blackroad-os-codex
```

---

## Step 2 — Run the Scanner

```bash
python3 blackroad-codex-scanner.py --repo .
```

Watch the output — you'll see components being discovered and saved.

---

## Step 3 — Verify the Results

```bash
python3 blackroad-codex-scraping-dashboard.py
```

You should see at least a handful of components listed.

---

## Step 4 — Search Your New Index

```bash
python3 blackroad-codex-search.py "scanner"
```

You'll see the scanner itself appear in the results — the Codex indexed itself! 🎉

---

## Next Steps

- Index more repos: `python3 blackroad-codex-scanner.py --repo /path/to/another/repo`
- Index everything: `./blackroad-codex-index-all.sh`
- Explore with search: [Advanced Search Techniques](advanced-search.md)
