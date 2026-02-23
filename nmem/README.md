# nmem

Cross-session memory for Claude Code. Captures observations from every session (file reads, edits, commands, errors), stores them in encrypted SQLite, and retrieves them via MCP tools.

## Install

1. Install the binary:

```sh
curl -fsSL https://raw.githubusercontent.com/viablesys/nmem/main/scripts/install.sh | sh
```

2. Restart Claude Code — the plugin activates automatically from the marketplace.

## Source

Full source, design docs, and ADRs: [viablesys/nmem](https://github.com/viablesys/nmem)

## License

MIT
