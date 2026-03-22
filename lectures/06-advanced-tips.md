# Lecture 06 — Tips, Tricks & Best Practices

---

## How to Write Good Prompts

Be specific — Claude does exactly what you say:

| Vague (avoid) | Specific (better) |
|---------------|-------------------|
| "Fix this" | "Fix the formatting so all dates are in DD/MM/YYYY format" |
| "Make it better" | "Rewrite this paragraph to be concise and professional" |
| "Do the thing" | "Create a backup copy of report.txt named report_backup_YYYY-MM-DD.txt" |

---

## The 3-Part Prompt Formula

```
[CONTEXT] + [TASK] + [CONSTRAINTS]
```

**Example:**
```
I run a small watch boutique in Italy (Locman).  ← CONTEXT
Write a short WhatsApp message to remind customers
about the spring collection launch on April 1st.  ← TASK
Keep it under 100 words, friendly, in Italian.   ← CONSTRAINTS
```

---

## Managing Costs

- Use **`/cost`** to check token usage in the current session
- Use **`/compact`** when a conversation gets very long — summarizes history to save tokens
- Use **Haiku** for simple tasks (much cheaper):
  ```bash
  claude --model claude-haiku-4-5-20251001
  ```
- Set a **monthly spending limit** in the Console → Settings → Billing

---

## Keeping Your API Key Safe

- **Never share** your API key with anyone
- **Never paste** it into a chat, email, or document
- If compromised: Console → API Keys → Delete it → Create a new one
- Each device should have its own named key (easy to revoke if lost)

---

## Best Practices

✅ **Do:**
- Be specific in your requests
- Tell Claude your context ("I run a hotel", "This is for my boss")
- Ask Claude to explain what it's doing if unsure
- Use `/clear` to start fresh when switching tasks
- Create a `CLAUDE.md` for folders you use regularly

❌ **Avoid:**
- Giving Claude access to sensitive financial accounts without care
- Sharing your API key
- Approving file changes without reading them first

---

## Everyday Use Ideas for Non-Programmers

- 📧 **Draft emails** in any language and tone
- 📊 **Analyze data** — "What's the trend in these sales numbers?"
- 📄 **Summarize documents** — "Summarize this contract in 5 bullet points"
- 🗂️ **Organize files** — "Sort these photos by year based on filename"
- 🔍 **Research** — "Search the web for competitors of Locman watches"
- 📝 **Create templates** — "Make a booking confirmation template for our hotel"
- 🌍 **Translation** — "Translate this invoice to English"

---

## When Claude Makes a Mistake

- **Review** any file changes before confirming
- **Ask Claude** to explain: "Why did you do that?"
- **Undo**: "Revert that last change"

---

➡️ **Next:** [Lecture 07 — Remote Access Setup](07-remote-access.md)
