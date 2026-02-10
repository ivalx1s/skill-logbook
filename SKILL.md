---
name: logbook
description: Record important findings, insights, decisions, and anomalies to a persistent Flight Logbook. Use proactively when discovering root causes, making architectural decisions, encountering surprising behavior, identifying regressions, completing significant milestones, or when the user says to log something. Invoke with 'review' to summarize the current logbook.
---

# Flight Logbook

Maintain a ship's-logbook-style record at `LOGBOOK.md` in the project root (visible, not hidden). This is the project's persistent institutional memory — concise, factual, high-signal.

## Standing Orders

1. **Read the logbook first** — read `LOGBOOK.md` before any write. If the file does not exist, create it with the header below.
2. **One entry per insight** — each entry is a single block under a timestamp. Never combine unrelated findings.
3. **Concise is mandatory** — every line must earn its place. No filler, no prose, no hedging. Telegraph style.
4. **Date grouping** — entries grouped under `## YYYY-MM-DD` headers (descending, newest on top). Add a new date header when the current date has no section.
5. **Timestamps** — 24h local time, format: `### HHmm — Short Title`.
6. **Review mode** — if invoked with `review`, read and summarize the logbook. Highlight unresolved items and recent patterns. Do not add an entry.

## Entry Format

```
## YYYY-MM-DD

### HHmm — Short Descriptive Title
- TAG: Detail
- TAG: Detail
```

## Tags (use as needed)

| Tag | Use for |
|-----|---------|
| `ROOT CAUSE` | Why a bug or failure happened |
| `FIX` | What changed and where |
| `FINDING` | Discovered behavior or fact |
| `DECISION` | Choice made and why |
| `REGRESSION` | Something that broke |
| `ANOMALY` | Unexplained behavior |
| `SCOPE` | Files/modules affected |
| `STATUS` | Resolved / pending / monitoring |
| `BLOCKED` | What prevents progress |
| `MILESTONE` | Significant checkpoint |
| `NOTE` | Anything else worth recording |

## New Logbook Header

When `LOGBOOK.md` does not exist, create it with:

```
# Flight Logbook

> Institutional memory. Concise, factual, high-signal.
> Newest entries first. One block per insight.
```

## Rules

- **Append-only** — never delete or rewrite past entries. Newest on top within each date.
- **No speculation** — only record what was observed or decided.
- **Link to code** — use `File.swift:123` or `path/file.py:45` references.
- **Arguments** — if text is passed after `/logbook`, treat it as entry content. Determine appropriate tags.
