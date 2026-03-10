# 🛠️ Installation Guide

**Prerequisites:** Python 3.11 or newer — that's it!

---

## Option A — One-Command Setup (Recommended)

```bash
git clone https://github.com/BlackRoad-OS/blackroad-os-codex.git
cd blackroad-os-codex
./setup.sh
```

The setup script will verify your Python version and prepare the Codex.

---

## Option B — Manual Steps

```bash
# 1. Clone the repo
git clone https://github.com/BlackRoad-OS/blackroad-os-codex.git
cd blackroad-os-codex

# 2. (Optional) Create a virtual environment
python3 -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

# 3. Verify Python version
python3 --version   # Should be 3.11+
```

> The Codex uses only Python standard-library modules (`ast`, `sqlite3`, `json`, `re`,
> `hashlib`, `pathlib`). No third-party packages are required.

---

## Verify the Install

```bash
python3 blackroad-codex-search.py "hello"
```

You should see search results (or "no results found") — either way, it's working!

---

## Docker (Optional)

```bash
docker build -t blackroad-codex .
docker run -it blackroad-codex
```

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| `python3: command not found` | Install Python 3.11+ from [python.org](https://www.python.org) |
| `Permission denied: ./setup.sh` | Run `chmod +x setup.sh` first |
| `sqlite3` errors | Ensure your Python was built with SQLite support (default on most systems) |

---

*See [QUICK_START.md](QUICK_START.md) for your first search.*
