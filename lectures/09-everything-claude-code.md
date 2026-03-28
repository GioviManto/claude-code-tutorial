# Lecture 09 — everything-claude-code: The Ultimate Plugin

> GitHub: https://github.com/affaan-m/everything-claude-code
> 50K+ stars · Anthropic Hackathon Winner · v1.9.0

This is a production-ready plugin system that transforms Claude Code from a chatbot into a full **agent orchestration platform**. It adds 60+ commands, 31 agents, 128 skills, 34 rule files, and a powerful hook system — all battle-tested over 10+ months of daily use.

---

## What You Get

| Component | Count | What it includes |
|-----------|-------|------------------|
| Commands | 60+ | `/plan`, `/tdd`, `/e2e`, `/code-review`, `/build-fix`, `/learn`, `/evolve`, `/security-scan`, ... |
| Agents | 31 | planner, architect, code-reviewer, tdd-guide, build-error-resolver, security-reviewer, ... |
| Skills | 128 | coding-standards, backend-patterns, frontend-patterns, TDD workflow, continuous-learning, ... |
| Rules | 34 | language-agnostic + language-specific (TypeScript, Python, Go, Java, Rust, Swift, ...) |
| Hooks | 15+ | SessionStart, PreToolUse, PostToolUse, Stop, PreCompact, SessionEnd |

---

## Installation (3 Options)

### Option 1 — Plugin Marketplace (Recommended)

Inside Claude Code, run:
```
/plugin marketplace add affaan-m/everything-claude-code
/plugin install everything-claude-code@everything-claude-code
```

### Option 2 — Manual Clone + Installer (What We Did)

```bash
# Clone into Claude's plugins folder
git clone https://github.com/affaan-m/everything-claude-code \
  ~/.claude/plugins/everything-claude-code

# Install dependencies
cd ~/.claude/plugins/everything-claude-code
npm install

# Run the installer for your profile
node scripts/install-apply.js --target claude --profile developer
```

### Option 3 — Per-Project (ecc-install.json)

Create an `ecc-install.json` in your project root:
```json
{
  "version": 1,
  "target": "claude",
  "profile": "developer",
  "include": ["lang:python", "capability:security"],
  "exclude": ["lang:java"]
}
```

Then run:
```bash
cd your-project
node ~/.claude/plugins/everything-claude-code/scripts/install-apply.js --config ecc-install.json
```

---

## Install Profiles

| Profile | Best for | Modules |
|---------|----------|---------|
| `core` | Minimal baseline | 6 modules |
| `developer` | Default for most developers | 9 modules |
| `security` | Security-focused projects | 7 modules |
| `research` | Content, research, writing | 9 modules |
| `full` | Everything | 19 modules |

---

## The Most Useful Commands

Once installed, use these inside any Claude Code session:

### Planning & Architecture
```
/plan          → Restate requirements, assess risks, create step-by-step plan
/multi-plan    → Collaborative planning with multiple model perspectives
```

### Development
```
/tdd           → Enforce test-driven development (write test first)
/e2e           → Generate and run Playwright end-to-end tests
/build-fix     → Fix build/compilation errors automatically
/code-review   → Full code quality review with actionable feedback
```

### Learning & Improvement
```
/learn         → Extract reusable patterns from this session
/evolve        → Cluster learned patterns into new skills (self-improving!)
/instinct-status → Show what Claude has learned from your sessions
```

### Context Management
```
/checkpoint    → Manually save session state
/aside         → Quick side question without breaking flow
/context-budget → Analyze how much context is being used
```

### Session Utilities
```
/security-scan → Scan for vulnerabilities (OWASP Top 10)
/docs          → Look up current library documentation
/model-route   → Recommend the best model for your current task
```

---

## How the Hooks Work Automatically

Once installed, these happen **without you doing anything:**

| Hook | What happens automatically |
|------|---------------------------|
| `SessionStart` | Loads your previous session context, detects package manager |
| `PreToolUse` (Bash) | Blocks `--no-verify` git flag, reminds you to use tmux for long commands |
| `PreToolUse` (Edit/Write) | Protects linter config files from being weakened, suggests compaction |
| `PostToolUse` (Edit) | Auto-formats JS/TS with Prettier/Biome, runs TypeScript type check |
| `PostToolUse` (Edit) | Warns about forgotten `console.log` statements |
| `Stop` | Saves session state, extracts patterns, tracks token cost |
| `Stop` | Sends a macOS desktop notification when Claude finishes a task |
| `PreCompact` | Saves state before the context window gets compressed |

---

## Continuous Learning System

One of the most powerful features: Claude **learns from your sessions** and improves over time.

```
/learn         → "What patterns from this session are worth keeping?"
               Claude extracts and saves reusable instincts

/instinct-status → Show all learned patterns (project + global)

/evolve        → "Cluster similar instincts into a new skill"
               Creates a new .md skill file automatically

/promote       → Move a project-scoped instinct to global (all projects)
```

This means every session makes Claude smarter for your specific workflow.

---

## Token Optimization Tips

ECC includes built-in cost management:

1. **Use Sonnet instead of Opus** — ~60% cheaper, handles 90% of tasks
   ```bash
   claude --model claude-sonnet-4-6
   ```

2. **Cap thinking tokens** in `~/.claude/settings.json`:
   ```json
   { "thinkingBudget": 10000 }
   ```

3. **Use `/compact` strategically** — ECC suggests it at logical breakpoints (the `suggest-compact` hook), rather than letting it happen automatically mid-task

4. **Use `/context-budget`** to see where your tokens are going

5. **Use Haiku for simple tasks:**
   ```bash
   claude --model claude-haiku-4-5-20251001 "Rename these files"
   ```

---

## Per-Project Integration

For each project you work on regularly, add an `ecc-install.json` to tailor what's installed:

**Python web project:**
```json
{
  "version": 1,
  "target": "claude",
  "profile": "developer",
  "include": ["lang:python", "framework:django", "capability:database"]
}
```

**TypeScript frontend:**
```json
{
  "version": 1,
  "target": "claude",
  "profile": "developer",
  "include": ["lang:typescript", "framework:react", "framework:nextjs"]
}
```

**Security-focused project:**
```json
{
  "version": 1,
  "target": "claude",
  "profile": "security",
  "include": ["capability:security"]
}
```

---

## Verify Your Installation

```bash
# Open Claude Code
claude

# Check all commands are available
/help

# Run the ECC diagnostic
/doctor

# Check what skills are loaded
/instinct-status

# See your token usage
/cost
```

You should see all the new `/plan`, `/tdd`, `/code-review` commands in `/help`.

---

## Resources

- GitHub: https://github.com/affaan-m/everything-claude-code
- Shorthand Guide: https://github.com/affaan-m/everything-claude-code/blob/main/the-shortform-guide.md
- Longform Guide: https://github.com/affaan-m/everything-claude-code/blob/main/the-longform-guide.md
- Security Guide: https://github.com/affaan-m/everything-claude-code/blob/main/the-security-guide.md
