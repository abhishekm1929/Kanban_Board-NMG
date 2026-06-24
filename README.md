# 🚀 Forge 2 · Edition 1 Qualifier — Kanban Board

A modern Trello-style Kanban Board built as part of the Forge 2 Qualifier using a multi-agent workflow powered by **Hermes** (planner) and **OpenClaw** (executor).

---

## 🎯 Project Overview

This project demonstrates how autonomous AI agents can collaborate to design, plan, and build a real-world task management application.

The system follows a Brain → Hands architecture:

* **Hermes** → Planning, task decomposition, coordination
* **OpenClaw** → Code generation, implementation, execution
* **Slack** → Agent communication layer
* **Human Approval Gate** → Final validation before delivery

---

## ✨ Features

### 📋 Kanban Board Management

* Create and manage boards
* Organize tasks into lists:

  * To Do
  * In Progress
  * Review
  * Done

### 📝 Card Management

* Create cards
* Edit card title and description
* Move cards between lists
* Delete cards

### 🏷️ Tags & Labels

Available labels:

* Bug
* Design
* Feature
* Docs
* Urgent

### 👥 Team Collaboration

Assign cards to team members:

* Alice
* Bob
* Carol
* Dave
* Eve

### 📅 Due Dates

* Add due dates to tasks
* Automatic overdue highlighting
* Better sprint tracking

---

## 🤖 AI Agent Architecture

| Agent    | Responsibility                              |
| -------- | ------------------------------------------- |
| Hermes   | Planning, orchestration, task decomposition |
| OpenClaw | Coding, implementation, execution           |
| Human    | Review and approval                         |
| Slack    | Communication channel                       |

Workflow:

Human Task
↓
Hermes
↓
OpenClaw
↓
Validation
↓
Human Approval
↓
Final Output

---

## 🧠 Models Used

| Agent    | Provider | Model                   | Purpose              |
| -------- | -------- | ----------------------- | -------------------- |
| Hermes   | Groq     | openai/gpt-oss-120b     | Planning & reasoning |
| OpenClaw | Groq     | llama-3.3-70b-versatile | Fast code generation |
| Fallback | Ollama   | qwen2.5-coder           | Local backup model   |

### Why These Models?

* GPT-OSS-120B provides strong reasoning and task planning.
* Llama 3.3 70B offers fast coding performance.
* Qwen Coder acts as an offline fallback when APIs are unavailable.

---

# 🌐 Live Demo

### Demo Application

https://kanbnn.netlify.app/

### Video Walkthrough

Add your Loom video link here.

Example:

https://loom.com/share/your-video-link

---

## ⚙️ Run Locally

### Frontend

```bash
cd frontend
npm install
npm run dev
```

Frontend runs on:

```text
http://localhost:5173
```

### Backend

```bash
cd backend
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
```

Backend runs on:

```text
http://localhost:8000
```

---

## 📂 Repository Structure

```text
.
├── backend/
├── frontend/
├── slack-export/
├── skills/
├── configs/
├── README.md
├── ARCHITECTURE.md
├── agent-log.md
├── .env.example
└── video.md
```

---

## 📖 Documentation

| File                         | Description                          |
| ---------------------------- | ------------------------------------ |
| README.md                    | Project overview                     |
| ARCHITECTURE.md              | Agent architecture and model routing |
| agent-log.md                 | Agent interaction history            |
| skills/task-planner/SKILL.md | Reusable Hermes skill                |
| slack-export/                | Slack communication evidence         |
| configs/                     | Hermes/OpenClaw configuration        |

---

## 📸 Evidence Included

✅ Slack communication screenshots

✅ Agent planning logs

✅ Architecture documentation

✅ Environment templates

✅ Skill definition

✅ Backend source code

✅ Frontend source code

✅ Deployment link

✅ Video walkthrough

---

## 🏆 Forge Qualifier Submission

Built for:

**Forge 2 – Edition 1 Qualifier**

Demonstrating:

* Multi-agent collaboration
* Autonomous task execution
* Slack-based communication
* AI-assisted software development
* Kanban project management

---

Made with ❤️ using Hermes, OpenClaw, Laravel, React, Groq and Slack.
