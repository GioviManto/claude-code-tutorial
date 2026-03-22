# Claude Code Cheatsheet

> Print this or keep it open during your first sessions!

---

## Installation

```bash
npm install -g @anthropic-ai/claude-code
```

---

## Starting Claude Code

```bash
claude                    # Start interactive session
claude "do something"     # One-off task
claude --help             # Show all options
```

---

## Slash Commands (inside the session)

| Command | Purpose |
|---------|--------|
| `/help` | Show all commands |
| `/clear` | Reset conversation |
| `/compact` | Summarize & compress history |
| `/cost` | Check token usage |
| `/exit` | Quit |
| `/model` | Switch model |
| `/doctor` | Diagnose issues |

---

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl+C` | Cancel / Exit |
| `↑` arrow | Previous message |

---

## Useful Prompt Patterns

```
"Read [filename] and summarize it"
"Create a file called [name] with [content]"
"Edit [file] to change [X] to [Y]"
"Find all files containing [word]"
"Rename all files in this folder that contain [X]"
"Search the web for [topic]"
"Translate this text to [language]: ..."
"Summarize this document in 5 bullet points"
```

---

## Models

| Model | Best for | Cost |
|-------|---------|------|
| `claude-haiku-4-5-20251001` | Quick & simple tasks | Cheapest |
| `claude-sonnet-4-6` | Most tasks, balanced | Medium |
| `claude-opus-4-6` | Complex reasoning | Highest |

Switch model:
```bash
claude --model claude-haiku-4-5-20251001
```

---

## Key Links

| Resource | Link |
|----------|------|
| Console & API Keys | https://console.anthropic.com |
| Official Docs | https://docs.anthropic.com/en/docs/claude-code/overview |
| Remote Help | https://remotedesktop.google.com/support |
| Pricing | https://www.anthropic.com/pricing |
