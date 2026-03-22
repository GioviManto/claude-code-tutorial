# Lecture 05 — Key Features & Slash Commands

---

## Slash Commands

Inside the Claude Code session, type special commands starting with `/`:

| Command | What it does |
|---------|-------------|
| `/help` | Show all available commands |
| `/clear` | Clear the conversation history |
| `/exit` | Quit Claude Code |
| `/compact` | Summarize conversation to save context |
| `/cost` | Show how many tokens this session has used |
| `/model` | Switch between Claude models |
| `/doctor` | Diagnose any setup issues |

---

## CLAUDE.md — Your Instruction File

Create a file called `CLAUDE.md` in any folder to give Claude **standing instructions** for that project:

```markdown
# CLAUDE.md

This folder contains files for our family holiday rental business.
- Always respond in Italian
- Never delete files without asking
- Keep all filenames in lowercase
```

Claude reads this file automatically every time you start a session in that folder.

---

## Working with Files

```
# Read a file
"Read invoice_march.pdf and tell me the total amount"

# Edit a file
"In the file guest_list.txt, add Marco Rossi with check-in March 30"

# Create files
"Create a folder called 'contracts' and put a template contract inside"

# Search across files
"Find all mentions of 'Locman' across all text files in this folder"
```

---

## Models You Can Use

```bash
# Fast and cheap — good for simple tasks
claude --model claude-haiku-4-5-20251001

# Balanced — good for most things (default)
claude --model claude-sonnet-4-6

# Most powerful — complex reasoning
claude --model claude-opus-4-6
```

---

## Multi-Step Tasks

Claude handles complex, multi-step tasks in one go:

```
"Look at all the PDF files in this folder, extract the
total amounts from each invoice, and create a summary
spreadsheet called totals.csv"
```

Claude will:
1. List the files
2. Read each PDF
3. Extract the data
4. Create the CSV

— all in one conversation.

---

## Permission System

By default, Claude **asks your permission** before writing files or running commands. You'll see prompts like:

```
⚠️  I'd like to write to invoice_summary.csv — allow? (y/n)
```

This keeps you in control. Always read these before approving.

---

➡️ **Next:** [Lecture 06 — Tips, Tricks & Best Practices](06-advanced-tips.md)
