# Lecture 07 — Remote Access Setup

This guide allows Giovanni to connect directly to your computer to help install and configure Claude Code — no need to describe problems, he can see and control your screen directly.

---

## Recommended Tool: Chrome Remote Desktop

**Why Chrome Remote Desktop?**
- 100% Free
- Works on Mac, Windows, Linux
- No account needed for the helper
- Secure: protected by a PIN you generate
- Works through all firewalls without special setup

---

## Setup for the Person Being Helped (Marco, Gloria, Vittoria)

### Step 1: Install Chrome Remote Desktop

1. Open **Google Chrome** (download at [google.com/chrome](https://www.google.com/chrome) if needed)
2. Go to: **[remotedesktop.google.com/access](https://remotedesktop.google.com/access)**
3. Click **"Download"** under "Set up remote access"
4. Install the extension when prompted
5. Click **"Turn on"** and follow the setup wizard
6. Set a PIN (at least 6 digits)

### Step 2: Share a One-Time Access Code

When ready for Giovanni to connect:
1. Go to **[remotedesktop.google.com/support](https://remotedesktop.google.com/support)**
2. Click **"Generate Code"** — a 12-digit code appears
3. **Send this code to Giovanni** (WhatsApp, phone call, etc.)
4. The code expires in **5 minutes** — generate it right when you're ready

---

## For Giovanni (the Helper)

### Connecting to Their Computer

1. Go to: **[remotedesktop.google.com/support](https://remotedesktop.google.com/support)**
2. Under "Connect to another computer", enter the 12-digit code
3. Click **"Connect"**
4. They confirm the connection on their screen

You now have **full control** of their mouse and keyboard.

### Once Connected — What to Do

```bash
# 1. Open their terminal
#    Mac: Cmd+Space → "Terminal"
#    Windows: Search → "PowerShell"

# 2. Check if Node.js is installed
node --version

# 3. Install Node.js if needed → nodejs.org

# 4. Install Claude Code
npm install -g @anthropic-ai/claude-code

# 5. Launch Claude Code
claude

# 6. Paste their API key when prompted
#    (they should have it ready from Lecture 01)
```

---

## Alternative: AnyDesk

If Chrome Remote Desktop doesn't work:

1. Download **AnyDesk** at [anydesk.com](https://anydesk.com) on **both** computers
2. The person opens AnyDesk → shares their **9-digit address**
3. Giovanni enters the address → clicks "Connect"
4. The other person clicks **"Accept"**

---

## Security Notes

- **Only share codes with people you fully trust**
- Chrome Remote Desktop codes expire after 5 minutes
- You can **disconnect** any time by closing the browser tab
- Never leave a remote session running unattended

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Code expired | Generate a new one |
| Connection refused | Make sure Chrome Remote Desktop is running on their computer |
| Too slow | Close other browser tabs on both computers |
| Can't see screen | Ask them to wake up their screen / disable screensaver |
