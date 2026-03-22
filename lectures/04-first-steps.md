# Lecture 04 — First Steps & Live Demo

Claude Code is installed. Let's explore what it can do.

---

## Starting Claude Code

```bash
claude
```

You're now in an **interactive session** — a live conversation with Claude.

To exit at any time: press `Ctrl+C` or type `/exit`

---

## Your First 5 Prompts

Try these one by one:

### 1. Ask a question
```
What is Claude Code and what can I do with it?
```

### 2. Create a file
```
Create a file called hello.txt with a friendly welcome message in Italian
```
Check your folder — the file was created!

### 3. Read and summarize
```
Read hello.txt and summarize what it says
```

### 4. Edit a file
```
Edit hello.txt and add today's date at the top
```

### 5. Explore your folder
```
What files are in my current directory?
```

---

## Running Claude on a Specific Folder

For best results, navigate to the folder you want to work in first:

```bash
cd Documents
claude
```

Now Claude has context of everything in your Documents folder.

---

## One-Off Commands (Without Entering Interactive Mode)

```bash
claude "What day is it today?"
claude "Summarize this document" report.pdf
```

---

## How Claude Understands Context

When you run `claude` from a folder, it reads a summary of all files in that directory. This means:

- You can say **"look at my invoice from last month"** and it will find the file
- You can say **"fix the error in my script"** without naming the file
- Claude remembers the **whole conversation** within a session

---

## What Claude Can Do For You

| Task | What to say |
|------|-------------|
| Write an email | "Write a professional email to my client about a delay" |
| Rename files | "Rename all JPG files in this folder to include today's date" |
| Explain an error | "I got this error, what does it mean: [paste error]" |
| Research | "Search the web for the best remote desktop tools" |
| Translation | "Translate this text to English" |
| Calculations | "Calculate the profit margin: revenue 50,000 cost 32,000" |
| Organize files | "Sort these invoices into folders by month" |

---

➡️ **Next:** [Lecture 05 — Key Features & Slash Commands](05-key-features.md)
