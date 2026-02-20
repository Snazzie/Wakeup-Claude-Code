# Wakeup Claude Code

A GitHub Action that keeps your Claude Code OAuth session alive by pinging it on a schedule every 5 hours.

Claude Code OAuth tokens expire after periods of inactivity. This repo runs a lightweight workflow automatically to prevent that.

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

That's it. The workflow runs automatically every 5 hours and on every manual trigger.

## Manual trigger

You can also trigger it manually from the **Actions** tab → **Claude 5-Hour Sync** → **Run workflow**.

## How it works

The workflow uses [`anthropics/claude-code-action`](https://github.com/anthropics/claude-code-action) to send a simple `"hi"` prompt with `claude-haiku` once per run. This is enough to keep the session token active without consuming meaningful credits.

## License

MIT
