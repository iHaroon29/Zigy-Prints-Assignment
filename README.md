<!-- WIP -->

# Node.js To-Do List App with TypeScript, Express, and MongoDB

This is a simple To-Do List application built using Node.js, TypeScript, Express, and MongoDB. The app allows users to create, retrieve, update, and delete tasks on their to-do list.

## Prerequisites

Before you begin, ensure you have the following installed:

- Node.js: Make sure you have Node.js installed on your machine.
- MongoDB: You should have a MongoDB server running locally or provide a remote connection URL.

## Installation

1. Clone this repository:

```bash
git clone https://github.com/yourusername/todo-list-app.git
```

2. Navigate to the project directory:

```bash
cd todo-list-app
```

3. Install dependencies:

```bash
npm install
```

4. Create a `.env` file in the root directory and provide the necessary environment variables:

```plaintext
PORT=3000
MONGODB_URI=mongodb://localhost:27017/todo-list
```

Replace the `MONGODB_URI` with your MongoDB connection URL.

5. Build the TypeScript code:

```bash
npm run build
```

6. Start the application:

```bash
npm start
```

The application should now be running on `http://localhost:3000`.

## API Endpoints

### Create a Task

- **Endpoint:** `POST /tasks`
- **Request Body:**

```json
{
  "title": "Buy groceries",
  "description": "Milk, eggs, bread",
  "dueDate": "2023-09-01"
}
```

- **Response (Success):** Status 201 Created

```json
{
  "message": "Task created successfully",
  "task": {
    "_id": "task_id",
    "title": "Buy groceries",
    "description": "Milk, eggs, bread",
    "dueDate": "2023-09-01",
    "createdAt": "timestamp"
  }
}
```

- **Response (Error):** Status 400 Bad Request

```json
{
  "error": "Validation failed",
  "message": "Title is required"
}
```

### Get All Tasks

- **Endpoint:** `GET /tasks`
- **Response (Success):** Status 200 OK

```json
{
  "tasks": [
    {
      "_id": "task_id1",
      "title": "Buy groceries",
      "description": "Milk, eggs, bread",
      "dueDate": "2023-09-01",
      "createdAt": "timestamp"
    },
    {
      "_id": "task_id2",
      "title": "Finish project",
      "description": "Complete the presentation",
      "dueDate": "2023-09-15",
      "createdAt": "timestamp"
    }
  ]
}
```

### Get Task by ID

- **Endpoint:** `GET /tasks/:taskId`
- **Response (Success):** Status 200 OK

```json
{
  "_id": "task_id",
  "title": "Buy groceries",
  "description": "Milk, eggs, bread",
  "dueDate": "2023-09-01",
  "createdAt": "timestamp"
}
```

- **Response (Error):** Status 404 Not Found

```json
{
  "error": "Task not found",
  "message": "The requested task could not be found"
}
```

### Update Task

- **Endpoint:** `PUT /tasks/:taskId`
- **Request Body:**

```json
{
  "title": "Buy groceries",
  "description": "Milk, eggs, bread and cheese",
  "dueDate": "2023-09-01"
}
```

- **Response (Success):** Status 200 OK

```json
{
  "message": "Task updated successfully",
  "task": {
    "_id": "task_id",
    "title": "Buy groceries",
    "description": "Milk, eggs, bread and cheese",
    "dueDate": "2023-09-01",
    "createdAt": "timestamp"
  }
}
```

- **Response (Error):** Status 404 Not Found

```json
{
  "error": "Task not found",
  "message": "The requested task could not be found"
}
```

### Delete Task

- **Endpoint:** `DELETE /tasks/:taskId`
- **Response (Success):** Status 200 OK

```json
{
  "message": "Task deleted successfully"
}
```

- **Response (Error):** Status 404 Not Found

```json
{
  "error": "Task not found",
  "message": "The requested task could not be found"
}
```

## Error Messages

- **400 Bad Request:** Indicates that the request is invalid or missing required parameters.
- **404 Not Found:** Indicates that the requested resource (task) could not be found.

## Conclusion

This To-Do List application provides basic functionality for managing tasks. You can extend and customize it according to your needs. Remember to handle errors and edge cases properly in a production environment. Happy coding!
