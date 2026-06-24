# Forge 2 · Edition 1 Qualifier — Kanban Board

A Trello-style Kanban board built by a two-agent system (Hermes + OpenClaw) wired through Slack.

## What the app does

- **Boards → Lists → Cards** — create a board; lists are To Do / In Progress / Review / Done; move cards between lists
- **Card details** — each card has a title, description, and is fully editable
- **Tags / labels** — coloured tags: `bug`, `design`, `feature`, `docs`, `urgent`
- **Assign a member** — assign any card to Alice, Bob, Carol, Dave, or Eve
- **Due date** — set a due date; overdue cards are visually flagged in red

## Models used

| Agent | Provider | Model | Why |
|-------|----------|-------|-----|
| Hermes (brain) | Groq | `openai/gpt-oss-120b` | Strongest free model for planning & decomposition |
| OpenClaw (hands) | Groq | `llama-3.3-70b-versatile` | Fast execution model for coding tasks |
| Fallback | Ollama (local) | `qwen2.5-coder` | Offline fallback when Groq rate-limits |

All models are **100% free**. No paid API keys used.

## Live URL

> **https://forge2-kanban.vercel.app** ← replace with your deployed URL

## Run locally

### Frontend (static — no build needed)
```bash
# Just open in browser
open frontend/index.html

# Or serve with any static server
npx serve frontend
```

### Backend (Laravel API)
```bash
cd backend
cp .env.example .env
composer install
php artisan key:generate
php artisan migrate          # SQLite — no DB server needed
php artisan serve            # runs on http://localhost:8000
```

### Full stack
```bash
# Terminal 1 — API
cd backend && php artisan serve

# Terminal 2 — Frontend (set VITE_API_URL=http://localhost:8000 in frontend/.env)
cd frontend && npm install && npm run dev
```

## Agent loop evidence
See `agent-log.md` for the full unedited chat log: human task → Hermes plan → OpenClaw code → status report.

## Slack evidence
See `slack-export/screenshots/` for proof of the chat loop and autonomous cron run.
