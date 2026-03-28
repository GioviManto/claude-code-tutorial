# Lecture 08 — Claude Code Advanced Concepts

Before we look at power-user plugins, let's build a solid mental model of how Claude Code is actually structured — and master the flags and modes that change how it behaves.

---

## The Four Building Blocks

### 1. Skills

A **skill** is a Markdown file that teaches Claude a workflow or domain knowledge. It tells Claude *how* to approach a specific type of task.

**Where they live:**
- Global: `~/.claude/skills/`
- Per-project: `.claude/skills/` inside your project folder

**Example skill: `tdd-workflow`**
```
When writing new code, always write the test first.
Run the test to confirm it fails.
Write the minimum code to pass.
Refactor.
```

When you invoke `/tdd` in Claude Code, it loads this skill and Claude follows it automatically.

> Skills are like teaching a person a technique once — they use it every time without being told again.

---

### 2. Hooks

A **hook** is an automation that fires automatically at specific lifecycle events — no prompt needed.

**Hook lifecycle events:**

| Event | When it fires |
|-------|---------------|
| `SessionStart` | When you open Claude Code |
| `PreToolUse` | Before Claude runs any tool (Bash, Edit, Write...) |
| `PostToolUse` | After any tool completes |
| `PreCompact` | Before context compaction |
| `Stop` | After each Claude response |
| `SessionEnd` | When you close Claude Code |

**Example hooks in action:**
- `SessionStart` → loads your previous session context automatically
- `PreToolUse` (Bash) → checks if you're accidentally bypassing git hooks
- `PostToolUse` (Edit) → auto-formats JS/TS files with Prettier/Biome
- `Stop` → saves session state, tracks cost, sends a desktop notification

**Hooks live in:** `~/.claude/settings.json` under the `"hooks"` key.

---

### 3. Agents

An **agent** is a specialized subagent Claude can delegate work to. Each agent is a Markdown file with a YAML frontmatter defining its name, description, tools, and model.

**Where they live:** `~/.claude/agents/`

**Examples of agents:**

| Agent | What it does |
|-------|-------------|
| `planner` | Creates step-by-step implementation plans |
| `code-reviewer` | Reviews code for quality, patterns, bugs |
| `tdd-guide` | Guides test-driven development |
| `architect` | Designs system architecture |
| `build-error-resolver` | Fixes compilation/build errors |
| `security-reviewer` | Scans for vulnerabilities |

You can invoke an agent explicitly: `"Use the planner agent to design this feature"` or Claude may invoke one automatically when appropriate.

---

### 4. Commands (Slash Commands)

A **command** is a Markdown file that defines a reusable workflow you trigger with `/`.

**Where they live:** `~/.claude/commands/`

**Most useful commands:**

| Command | What it does |
|---------|-------------|
| `/plan` | Restate requirements, assess risks, plan implementation |
| `/tdd` | Enforce test-driven development for current task |
| `/code-review` | Full code quality review |
| `/e2e` | Generate and run end-to-end tests |
| `/build-fix` | Fix build/compilation errors |
| `/learn` | Extract reusable patterns from this session |
| `/evolve` | Cluster learned patterns into new skills |
| `/checkpoint` | Save session state manually |
| `/aside` | Answer a quick side question without interrupting flow |

**Per-project commands:** create `.claude/commands/my-command.md` in any project folder for project-specific shortcuts.

---

## Important Flags & Modes

### Auto Mode

```bash
claude --auto
```

Claude runs in **fully autonomous mode** — it completes multi-step tasks without asking for confirmation at each step. Great for complex tasks where you trust Claude to proceed.

> Use with care in production environments.

---

### Dangerously Skip Permissions

```bash
claude --dangerously-skip-permissions
```

Bypasses all permission prompts — Claude writes files, runs commands, and edits without asking you first.

**When to use:**
- Inside a sandboxed environment (Docker, VM)
- Automated pipelines and CI/CD
- When you fully trust the task and environment

**When NOT to use:**
- On your main machine with sensitive files
- When working in production repos
- When you're not sure what Claude will do

> This is also what `skipDangerousModePermissionPrompt: true` in `settings.json` enables permanently.

---

### Choosing Your Model

```bash
claude --model claude-haiku-4-5-20251001   # Fast, cheap — simple tasks
claude --model claude-sonnet-4-6           # Balanced — most tasks (default)
claude --model claude-opus-4-6             # Most powerful — complex reasoning
```

**Rule of thumb:**
- Start with **Sonnet** (default) — it handles 90% of tasks well
- Switch to **Haiku** for quick questions, file renames, simple edits (~60% cheaper)
- Use **Opus** only for architecture decisions, complex debugging, or deep research

You can also switch models mid-session with `/model`.

---

### Cap Token Usage (Cost Control)

Add this to `~/.claude/settings.json` to cap thinking tokens:
```json
{
  "thinkingBudget": 10000
}
```

The default is 31,999 — capping at 10,000 reduces cost significantly for most tasks.

---

### Useful Startup Flags

```bash
# Work in a specific directory
claude --add-dir ~/Documents/my-project

# Run a task and exit (non-interactive)
claude -p "Summarize all TODO comments in this codebase"

# Resume last session
claude --resume

# Check version and setup
claude --version
claude /doctor
```

---

## CLAUDE.md — Your Project Instruction File

Create `CLAUDE.md` at the root of any project to give Claude standing instructions:

```markdown
# CLAUDE.md

## Project Context
This is the Locman watch boutique website.
Language: Python/Django backend, vanilla JS frontend.

## Rules
- Always respond in Italian when asked about the business
- Never commit directly to main — always use a branch
- Run tests before every commit
- Keep all prices in EUR
```

Claude reads this **automatically** every session in that folder. No need to repeat yourself.

**Global CLAUDE.md:** `~/.claude/CLAUDE.md` applies to all projects.

---

## Settings.json Quick Reference

`~/.claude/settings.json` controls Claude Code's global behavior:

```json
{
  "skipDangerousModePermissionPrompt": true,
  "thinkingBudget": 10000,
  "env": {
    "MY_VAR": "value"
  },
  "hooks": {
    "SessionStart": [...],
    "PreToolUse": [...],
    "PostToolUse": [...],
    "Stop": [...]
  }
}
```

---

➡️ **Next:** [Lecture 09 — everything-claude-code Plugin](09-everything-claude-code.md)
