# Session Journals

This directory contains session journals for Venture Factory Test.

## Format

Journals follow the zeOS session journaling standard:
- Filename: `YYYY-MM-DD-NNN.md` or `{prefix}-NNN.md`
- Status: CHECKPOINT or COMPLETE
- Required fields: session_id, date, status, agent, next_action_primer

## YAML Header Template

```yaml
---
session_id: "YYYY-MM-DD-NNN"
date: "YYYY-MM-DD"
status: "ACTIVE | CHECKPOINT | COMPLETE"
agent: "Claude (Persistence Executor)"
profile: "richie"
application: "Venture Factory Test"
phase: "[Current phase from MASTER_ROADMAP.md]"
next_action_primer: "One-line summary for boot greeting"
constraints_carried:
  - "Constraint 1"
  - "Constraint 2"
last_artifact: "Path or description"
---
```

## Shell Commands

- `!checkpoint [note]` — Save progress mid-session
- `!end` — Generate final journal and commit
- `!log` — Display current session state

## Journal Lifecycle

```
ACTIVE → CHECKPOINT → ... → COMPLETE
```

Sessions should always end with `!end` to ensure proper handoff.

---

See zeOS Shell Protocol for full documentation.
