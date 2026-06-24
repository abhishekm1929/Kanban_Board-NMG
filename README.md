# 🚀 Forge 2 Edition 1 – Kanban Board

### 🌐 Live Demo

**https://kanbnn.netlify.app/**

### 🎥 Video Walkthrough

**https://drive.google.com/file/d/1dl-iZdYd31CdeIQNxQfPzMau68DxNJ5D/view?usp=sharing**

---

## Overview

A Trello-style Kanban Board built using a multi-agent workflow powered by **Hermes** (planner) and **OpenClaw** (executor).

### Features

* 📋 Boards, Lists, and Cards
* ✏️ Edit card title & description
* 🏷️ Tags (Bug, Design, Feature, Docs, Urgent)
* 👥 Assign members to tasks
* 📅 Due dates with overdue highlighting
* 🔄 Move cards across workflow stages

---

## Agent Architecture

```text
Human
  ↓
Hermes (Planning)
  ↓
OpenClaw (Coding)
  ↓
Validation
  ↓
Final Output
```

---

## Models Used

| Agent    | Model                  |
| -------- | ---------------------- |
| Hermes   | GPT-OSS-120B (Groq)    |
| OpenClaw | Llama-3.3-70B (Groq)   |
| Fallback | Qwen2.5-Coder (Ollama) |

---

## Run Locally

### Frontend

```bash
cd frontend
npm install
npm run dev
```

### Backend

```bash
cd backend
composer install
php artisan serve
```

---

## Repository Contents

* `README.md`
* `ARCHITECTURE.md`
* `agent-log.md`
* `slack-export/`
* `skills/task-planner/SKILL.md`
* `configs/`
* `frontend/`
* `backend/`
* `.env.example`

---

Built for **Forge 2 Edition 2 Qualifier** 🚀
