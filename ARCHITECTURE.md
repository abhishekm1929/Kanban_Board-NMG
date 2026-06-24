# Architecture — Forge 2 Qualifier

## Agent roles

| Agent | Tool | Role | Nickname |
|-------|------|------|----------|
| **Hermes** | NousResearch/hermes-agent | Plans tasks, holds memory, runs on schedule, orchestrates OpenClaw | *the brain* |
| **OpenClaw** | github.com/openclaw/openclaw | Receives tasks, writes code, executes it, reports results | *the hands* |

## Slack channel scheme

| Channel | Who posts | Purpose |
|---------|-----------|---------|
| `#sprint-main` | You + Hermes | Human posts goals → Hermes posts plan → decisions land here |
| `#agent-coder` | Hermes + OpenClaw | Hermes assigns coding tasks → OpenClaw writes/runs code → posts `What I Did / What's Left / What Needs Your Call` |
| `#agent-log` | Both agents | Raw activity log, autonomous cron output, full audit trail |

## The loop

```
You (#sprint-main)
  → describe goal
  → Hermes posts plan + task breakdown
  → You approve

Hermes (#agent-coder)
  → assigns Task 1 to OpenClaw
  → OpenClaw writes code, runs it
  → OpenClaw reports "What I Did / What's Left / What Needs Your Call"
  → You review / correct in #sprint-main

Hermes (cron)
  → every 10 min: posts one-line progress update to #sprint-main
  → no human prompt needed (autonomous run)
```

## Model routing

```
Hermes  (planning / memory / decomposition)
  → Groq: openai/gpt-oss-120b        ← primary (strongest free)
  → Fallback: gemini-2.5-flash        ← if Groq rate-limits

OpenClaw  (code writing / execution)
  → Groq: llama-3.3-70b-versatile    ← primary (fast coder)
  → Fallback: Ollama qwen2.5-coder   ← unlimited local fallback
```

**Why this routing:** Hermes does the heavy reasoning (planning, memory search, skill matching) so it gets the 120b model. OpenClaw executes well-scoped tasks, so the 70b model is fast enough and saves Groq TPM for Hermes.

## Tech stack

```
Backend   Laravel 11 (PHP 8.2+)  REST API  SQLite database
Frontend  React 18 + Vite        Talks to Laravel API
Hosting   Vercel (frontend)      Render free tier (API)
```

## Key files

```
skills/status-report/SKILL.md   ← Hermes reusable skill (fires on status requests)
openclaw.json                   ← OpenClaw config (secrets removed; see .env.example)
agent-log.md                    ← Unedited agent chat transcript
slack-export/screenshots/       ← Proof: chat loop + autonomous run + round-trip test
```
