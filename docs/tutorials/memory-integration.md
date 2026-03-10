# 🔗 Memory Integration Tutorial

How to use the Codex together with the BlackRoad Memory system for perfect team coordination.

---

## The Two-Check System

Before writing any new code, always check both systems:

1. **[MEMORY]** — See what other agents/developers are working on right now
2. **[CODEX]** — Search for existing implementations

This prevents:
- Duplicate work across the team
- Conflicting changes to the same files
- Rebuilding code that already exists

---

## Quick Integration

```bash
# 1. Register your session with memory
MY_CLAUDE=$(~/memory-sync-daemon.sh register "my-task")

# 2. Check what others are doing
~/memory-realtime-context.sh live $MY_CLAUDE compact

# 3. Search the Codex for existing code
python3 blackroad-codex-search.py "the feature I'm about to build"

# 4. If nothing exists, announce your work
~/memory-system.sh log announce "$MY_CLAUDE" "
[MEMORY] ✅ Checked — no conflicts
[CODEX]  ✅ Searched — no existing implementation
Working on: my-new-feature
"
```

---

## The Golden Rules

| Rule | Why |
|------|-----|
| **If [CODEX] has it, USE IT** | Avoid rebuilding existing code |
| **If [MEMORY] shows a conflict, COORDINATE** | Prevent merge nightmares |
| **Always announce before starting** | Keep the team informed |

---

## Full Guide

See [MEMORY_CODEX_INTEGRATION.md](../MEMORY_CODEX_INTEGRATION.md) for the complete integration documentation.
