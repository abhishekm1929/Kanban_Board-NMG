## Backend API

### Overview

The backend is a lightweight RESTful API built with PHP and SQLite. It powers the Kanban Board application by managing boards, lists, cards, members, tags, and task updates through JSON-based endpoints.

### Features

* Create, update, and delete boards
* Create and manage task lists
* Create, edit, move, and delete cards
* Assign members to tasks
* Add tags and due dates
* SQLite database with automatic initialization and seed data
* JSON API responses
* CORS enabled for frontend integration

### Tech Stack

* PHP 8.2+
* SQLite
* REST API Architecture

### Project Structure

backend/
├── index.php
├── database.sqlite
└── README.md

### Requirements

* PHP 8.2 or later

### Run Locally

1. Navigate to the backend directory:

```bash
cd backend
```

2. Start the PHP development server:

```bash
php -S localhost:8000 index.php
```

3. Open the API:

```text
http://localhost:8000/api/boards
```

### Available Endpoints

| Method | Endpoint          | Description    |
| ------ | ----------------- | -------------- |
| GET    | /api/boards       | Get all boards |
| POST   | /api/boards       | Create board   |
| PUT    | /api/boards/{id}  | Update board   |
| DELETE | /api/boards/{id}  | Delete board   |
| POST   | /api/lists        | Create list    |
| PUT    | /api/lists/{id}   | Update list    |
| DELETE | /api/lists/{id}   | Delete list    |
| POST   | /api/cards        | Create card    |
| PUT    | /api/cards/{id}   | Update card    |
| DELETE | /api/cards/{id}   | Delete card    |
| POST   | /api/members      | Create member  |
| DELETE | /api/members/{id} | Delete member  |

### Sample Data

The application automatically seeds a demo board with:

* To Do
* Doing
* Done

lists, sample members, and example task cards for quick testing.

### Architecture

Frontend (HTML/CSS/JavaScript)
↓
REST API (PHP)
↓
SQLite Database

The backend follows a simple REST architecture with SQLite persistence, making it lightweight, portable, and easy to deploy.
