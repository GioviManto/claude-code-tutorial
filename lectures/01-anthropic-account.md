# Lecture 01 — Creating Your Anthropic Account

To use Claude Code, you need an **Anthropic account** and an **API key**.

---

## Step 1: Create an Account

1. Go to **[console.anthropic.com](https://console.anthropic.com)**
2. Click **"Sign up"**
3. You can sign up with:
   - Your Google account (easiest)
   - Or email + password
4. Verify your email if prompted

---

## Step 2: Add a Payment Method

Claude Code uses a **pay-as-you-go** pricing model. You are only charged for what you use.

1. In the Console, go to **Settings → Billing**
2. Add a credit card
3. Set a **usage limit** to stay in control (e.g., $10/month to start)

> 💡 **Typical cost:** For casual use, expect **$1–5 per month**. Heavy developer usage might be $10–30/month.

---

## Step 3: Create an API Key

This is the "password" that links Claude Code on your computer to your Anthropic account.

1. In the Console, click **"API Keys"** in the left sidebar
2. Click **"Create Key"**
3. Give it a name (e.g., `my-macbook` or `home-computer`)
4. **Copy the key immediately** — it will only be shown once!
5. Save it somewhere safe (Notes app, password manager)

Your key looks like:
```
sk-ant-api03-XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
```

---

## Step 4: The Key Goes Into Claude Code

When you first run `claude` in your terminal, it will ask for your API key. You paste it there. Claude Code stores it securely — you only need to do this once per computer.

---

## Pricing Reference

| Model | Input cost | Output cost |
|-------|-----------|-------------|
| Claude Sonnet 4.6 | $3 / 1M tokens | $15 / 1M tokens |
| Claude Haiku 4.5 | $0.80 / 1M tokens | $4 / 1M tokens |

> A "token" is roughly ¾ of a word. A typical conversation uses a few thousand tokens.

Full pricing: [anthropic.com/pricing](https://www.anthropic.com/pricing)

---

➡️ **Next:** [Lecture 02 — Prerequisites](02-prerequisites.md)
