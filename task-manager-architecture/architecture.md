# Task Manager Web App – Architecture Document

## 1. Product Idea

**Task Manager** is a small web application designed to help users organize daily tasks in one place.

A user can create tasks, view existing tasks, update task information, mark tasks as completed, and delete tasks.

The application is planned as a full-stack web application with a JavaScript-based frontend and Node.js backend.

---

## 2. Target Users

The application is intended for students, beginners, and anyone who wants a simple way to manage personal tasks.

---

## 3. Core Features

1. User registration and login
2. Create a new task
3. View all tasks
4. View individual task details
5. Edit an existing task
6. Mark a task as completed
7. Delete a task
8. Filter tasks by status

---

## 4. Data Models

### User

| Field | Type | Description |
|---|---|---|
| id | String/ObjectId | Unique user ID |
| name | String | User's name |
| email | String | User email |
| password | String | Hashed password |
| createdAt | Date | Account creation date |

### Task

| Field | Type | Description |
|---|---|---|
| id | String/ObjectId | Unique task ID |
| title | String | Task title |
| description | String | Task details |
| status | String | pending/completed |
| priority | String | low/medium/high |
| dueDate | Date | Optional deadline |
| userId | String/ObjectId | Owner of the task |
| createdAt | Date | Task creation date |
| updatedAt | Date | Last update time |

---

## 5. API Routes

### Authentication

| Method | Route | Purpose |
|---|---|---|
| POST | `/api/auth/register` | Create a user account |
| POST | `/api/auth/login` | Log in a user |

### Tasks

| Method | Route | Purpose |
|---|---|---|
| GET | `/api/tasks` | Get all tasks for the logged-in user |
| POST | `/api/tasks` | Create a new task |
| GET | `/api/tasks/:id` | Get one task |
| PUT | `/api/tasks/:id` | Update a task |
| PATCH | `/api/tasks/:id/status` | Change task status |
| DELETE | `/api/tasks/:id` | Delete a task |

---

## 6. Frontend Screens

### 1. Login Screen
- Email input
- Password input
- Login button
- Registration link

### 2. Registration Screen
- Name input
- Email input
- Password input
- Register button

### 3. Dashboard
- Navigation/header
- Task summary
- Task list
- Filter by status
- Add Task button

### 4. Add Task Screen
- Task title
- Description
- Priority
- Due date
- Save button

### 5. Edit Task Screen
- Existing task information
- Update button
- Delete option

### 6. Task Details
- Full task information
- Status
- Priority
- Due date
- Edit and delete actions

---

## 7. System Architecture

```text
+-----------------------------+
|           User              |
+--------------+--------------+
               |
               v
+-----------------------------+
| Frontend                    |
| HTML + CSS + JavaScript     |
+--------------+--------------+
               |
          HTTP / REST
               |
               v
+-----------------------------+
| Backend                     |
| Node.js + Express.js        |
| Authentication + API Logic  |
+--------------+--------------+
               |
               v
+-----------------------------+
| Database                    |
| MongoDB                     |
+-----------------------------+
```

---

## 8. Suggested Project Structure

```text
task-manager-architecture/
│
├── README.md
├── architecture.md
│
├── frontend/
│   ├── index.html
│   ├── css/
│   │   └── style.css
│   └── js/
│       └── app.js
│
└── backend/
    ├── server.js
    ├── routes/
    ├── controllers/
    ├── models/
    └── middleware/
```

This repository is currently a **starter architecture repository**. Implementation can be added in later development tasks.

---

## 9. Example User Flow

```text
User opens application
        |
        v
     Login
        |
        v
    Dashboard
        |
        +----> Add Task
        |
        +----> View Task
        |
        +----> Edit Task
        |
        +----> Complete Task
        |
        +----> Delete Task
```

---

## 10. Future Improvements

- Search tasks
- Task categories
- Notifications/reminders
- Dark mode
- Responsive mobile UI
- JWT-based authentication
- Admin dashboard
- Deployment using a cloud platform

---

## 11. Conclusion

The proposed architecture separates the application into three major layers:

1. **Frontend** – user interface and interaction
2. **Backend** – business logic and REST APIs
3. **Database** – persistent storage of users and tasks

This structure keeps the application organized and allows each layer to be developed and maintained independently.
