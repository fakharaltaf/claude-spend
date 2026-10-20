# claude-spend

Check your estimated Claude Code spend across **all** your local sessions at once, instead of opening each session and running `/usage` one by one.

It's a thin wrapper around [ccusage](https://github.com/ryoppippi/ccusage), which reads the session transcripts Claude Code stores in `~/.claude/projects/`.

## Install

Requires macOS (it uses BSD `date`), zsh and Node.js (for `npx`).

```sh
curl -fsSL https://raw.githubusercontent.com/fakharaltaf/claude-spend/main/claude-spend -o ~/.local/bin/claude-spend
chmod +x ~/.local/bin/claude-spend
```

Make sure `~/.local/bin` is on your `PATH`.

## Usage

| Command | Shows |
|---|---|
| `claude-spend` | Monthly totals + last 7 days |
| `claude-spend today` | Today only |
| `claude-spend week` | Last 7 days, per day |
| `claude-spend month` | This month, per day |
| `claude-spend sessions` | One row per session |
| `claude-spend --help` | Command list |

Any other arguments are passed straight to ccusage, e.g. `claude-spend daily --since 20261001`.

Inside Claude Code you can run it without leaving the session: `! claude-spend`.

## Caveats

- Costs are **estimates** at API list prices, not your actual invoice. Check your billing dashboard for real spend.
- Only sessions run on the current machine are counted — not other machines, cloud sessions or claude.ai chats.
- ccusage is pinned to `20.0.37` so the script doesn't pull unreviewed new versions on every run. Bump the version in the script to update.

## License

MIT
