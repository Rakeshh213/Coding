# Task Manager Web App – Project Architecture

## Task 1: Project Architecture

A simple full-stack Task Manager application where users can create, view, update, complete, and delete tasks.

### Planned Technology Stack

- **Frontend:** HTML, CSS, JavaScript
- **Backend:** Node.js, Express.js
- **Database:** MongoDB
- **API Style:** REST API

### Main Features

- User registration/login
- Create a task
- View all tasks
- View task details
- Edit a task
- Mark a task as completed
- Delete a task

### Architecture

```text
User
  |
  v
Frontend (HTML/CSS/JavaScript)
  |
  | HTTP / REST API
  v
Backend (Node.js + Express.js)
  |
  v
MongoDB Database
```

See [architecture.md](architecture.md) for the complete architecture document.
