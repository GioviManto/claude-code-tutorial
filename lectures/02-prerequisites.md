# Lecture 02 — Prerequisites: Node.js & Terminal Basics

Before installing Claude Code, you need two things:
1. **Node.js** (the software that runs Claude Code)
2. Basic comfort with the **terminal** (we'll cover this now)

---

## Part A: The Terminal

### What is the Terminal?

The terminal is a text-based window where you type commands directly to your computer. It sounds scary but you'll only need a handful of commands.

**Opening the Terminal:**

| System | How to Open |
|--------|-------------|
| **Mac** | Press `Cmd + Space`, type `Terminal`, press Enter |
| **Windows** | Press `Win`, type `PowerShell`, press Enter |

### Essential Commands

```bash
# See where you are
pwd

# List files in current folder
ls         # Mac
dir        # Windows

# Move into a folder
cd Documents

# Go back up one level
cd ..

# Clear the screen
clear      # Mac
cls        # Windows
```

> 💡 **Tip:** Once Claude Code is running, you can just ask it in plain language — you barely need these commands!

---

## Part B: Installing Node.js

### Check if You Already Have It

Open the terminal and type:
```bash
node --version
```

If you see `v18.x.x` or higher — you're good! Skip to the next lecture.

If you get an error — follow the steps below.

---

### Install Node.js on Mac

1. Go to [nodejs.org](https://nodejs.org)
2. Download the **LTS** version (left button)
3. Run the `.pkg` installer — follow all defaults
4. Open a **new** terminal window and run `node --version` to confirm

### Install Node.js on Windows

1. Go to [nodejs.org](https://nodejs.org)
2. Download the **LTS** installer (`.msi` file)
3. Run it — click Next through everything
4. ✅ Make sure **"Add to PATH"** is checked
5. Restart PowerShell and run `node --version`

---

### Verify Installation

```bash
node --version   # Should show v18.x.x or higher
npm --version    # Should show a version number
```

Both must work before proceeding.

---

➡️ **Next:** [Lecture 03 — Installing Claude Code](03-installation.md)
