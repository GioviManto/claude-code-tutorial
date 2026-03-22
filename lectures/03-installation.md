# Lecture 03 — Installing Claude Code

Now that you have Node.js, installing Claude Code takes **one command**.

---

## Installation

Open your terminal and run:

```bash
npm install -g @anthropic-ai/claude-code
```

- `npm` = Node Package Manager (comes with Node.js)
- `install -g` = install globally (available from anywhere on your computer)
- `@anthropic-ai/claude-code` = the official package name

This downloads and installs Claude Code. It takes 1–2 minutes.

---

## First Launch

After installation, run:

```bash
claude
```

The first time, Claude Code will:
1. Ask you to **paste your API key** (from Lecture 01)
2. Show you the terms of service — type `yes` to accept
3. Open the interactive session

You'll see:
```
✓ Claude Code v1.x.x
> How can I help you today?
```

**You're in!** 🎉

---

## Troubleshooting

### "Permission denied" on Mac

```bash
sudo npm install -g @anthropic-ai/claude-code
```
(Enter your Mac password when asked)

### "command not found: claude" after installing

Close the terminal, open a new one, and try again.

### Windows: "running scripts is disabled"

Open PowerShell **as Administrator** and run:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```
Then try installing again.

### Need to re-enter your API key

```bash
claude config set api_key sk-ant-api03-YOURKEY
```

---

## Updating Claude Code

```bash
npm update -g @anthropic-ai/claude-code
```

---

➡️ **Next:** [Lecture 04 — First Steps & Live Demo](04-first-steps.md)
