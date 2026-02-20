# Wakeup Claude Code

A GitHub Action that pre-starts your Claude Code session so the usage window is already ticking before you sit down to code.

## The Problem

Claude Code usage limits reset on a timer. When you start coding, that kicks off a fresh session — meaning if you code hard, you might hit the wall and then have to wait the full window out before the limit resets.

## The Solution

This workflow fires a session every 5 hours in the background. When you sit down to code, your session was already started hours ago — so a reset is coming sooner. You're less likely to hit the limit mid-flow and get stuck waiting.

## Setup

### 1. Fork this repository

Click **Fork** at the top right of this page.

### 2. Get your Claude Code OAuth token

On your local machine, run:

```bash
claude setup-token
```

Copy the token it outputs.

### 3. Add the token as a repository secret

In your forked repo:

1. Go to **Settings** → **Secrets and variables** → **Actions**
2. Click **New repository secret**
3. Name: `CLAUDE_CODE_OAUTH_TOKEN`
4. Value: paste your token from step 2
5. Click **Add secret**

### 4. Enable Actions

If GitHub Actions are disabled on your fork, go to the **Actions** tab and enable them.

The workflow will now run automatically at **1am, 6am, 11am, 4pm, and 9pm UTC** every day.

## License

MIT
