# nmem — Cross-Session Memory

nmem is recording this session. It captures observations (file reads, edits, commands, errors) and retrieves them via MCP tools. **Query it before re-deriving solutions.**

## MCP Tools

| Tool | Purpose |
|------|---------|
| `search` | FTS5 full-text search over observations (AND/OR/NOT, phrases, prefix*). Filter by project or obs_type. |
| `get_observations` | Fetch full observation details by ID after finding them via search. |
| `recent_context` | Recent observations ranked by recency + type weight + project match. |
| `session_summaries` | Structured summaries of past sessions: intent, learned, completed, next_steps. |
| `timeline` | Observations surrounding an anchor point within the same session. |
| `file_history` | Trace a file's history across sessions with intent context. |
| `session_trace` | Step-by-step session replay. |
| `current_stance` | Current session's cognitive trajectory and retrieval guidance. |
| `queue_task` | Queue a task for later dispatch. |
| `create_marker` | Record a decision or conclusion. |
| `regenerate_context` | Re-run context injection with current data. |

## Retrieval Triggers

- **First contact with a file or module** — run `file_history` before acting.
- **Design question or investigation** — `session_summaries` for prior `learned` entries.
- **Build or test failure** — `search` for the error pattern filtered to `command` obs_type.
- **Scope shift** — new work starting. Check `session_summaries` for relevant `next_steps`.
- **Before committing to an approach** — `search` for the approach name. Prior sessions may have tried and abandoned it.

One query costs nothing; re-deriving a prior conclusion costs the full investigation again.
