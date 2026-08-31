# Practical 4: Task Management RESTful API with Express.js

##  Overview
This project is a RESTful Web API built with **Node.js** and **Express.js** for managing tasks. It demonstrates core backend architecture concepts including modular routing, custom request logging middleware, global error handling, and standard CRUD operations.

---

##  Features
-  **Task Management (CRUD)**: Create, Read, Update, and Delete tasks.
-  **Custom Logger Middleware**: Logs every incoming HTTP request method, URL, and timestamp to the console.
-  **Global Error Handler**: Catches unhandled errors and returns structured JSON responses with HTTP `500` status codes.
-  **404 Route Handler**: Handles undefined routes gracefully with a structured `404 Not Found` response.
-  **Modular Folder Architecture**: Separates routing, custom middleware, and core application logic.

---

## Project Structure

```
prac4/
├── middleware/
│   ├── logger.js        # Request logging middleware
│   └── errorHandler.js  # Global error handling middleware
├── routes/
│   └── taskRoutes.js    # Task CRUD routes (GET, POST, PUT, DELETE)
├── app.js               # Application entry point & server setup
├── package.json         # Project dependencies & scripts
├── package-lock.json    # Dependency lock file
└── README.md            # Project documentation
```

---

## Prerequisites & Installation

### Prerequisites
- [Node.js](https://nodejs.org/) (v14 or higher recommended)
- [npm](https://www.npmjs.com/) (Node Package Manager)


##  API Endpoint Documentation

Base URL: `http://localhost:3000`

### 1. Get All Tasks
- **Endpoint**: `GET /tasks`
- **Description**: Retrieves a list of all tasks.
- **Response** (`200 OK`):
  ```json
  [
    {
      "id": 1,
      "title": "Learn Node.js",
      "completed": false
    }
  ]
  ```

---

### 2. Create a New Task
- **Endpoint**: `POST /tasks`
- **Description**: Adds a new task to the task list.
- **Request Body**:
  ```json
  {
    "title": "Build a REST API",
    "completed": false
  }
  ```
- **Response** (`201 Created`):
  ```json
  {
    "message": "Task created successfully",
    "task": {
      "id": 2,
      "title": "Build a REST API",
      "completed": false
    }
  }
  ```

---

### 3. Update a Task
- **Endpoint**: `PUT /tasks/:id`
- **Description**: Updates an existing task by its ID.
- **Request Body**:
  ```json
  {
    "title": "Learn Express.js Middleware",
    "completed": true
  }
  ```
- **Response** (`200 OK`):
  ```json
  {
    "message": "Task updated successfully",
    "task": {
      "id": 1,
      "title": "Learn Express.js Middleware",
      "completed": true
    }
  }
  ```
- **Error Response** (`404 Not Found`):
  ```json
  {
    "message": "Task not found"
  }
  ```

---

### 4. Delete a Task
- **Endpoint**: `DELETE /tasks/:id`
- **Description**: Removes a task by its ID.
- **Response** (`200 OK`):
  ```json
  {
    "message": "Task deleted successfully"
  }
  ```
- **Error Response** (`404 Not Found`):
  ```json
  {
    "message": "Task not found"
  }
  ```

---

##  Technologies Used
- **Node.js**: JavaScript runtime environment.
- **Express.js**: Web framework for Node.js.
- **JavaScript (ES6+)**: Programming language.
