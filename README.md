# backend
Task Manager Backend API
This is a simple REST API for managing tasks, built with Node.js and Express.js for an internship entrance challenge. It uses an in-memory array to store task data, meaning data will reset each time the server restarts.

Features
GET /api/tasks: Retrieve all tasks.

Supports filtering:

GET /api/tasks?completed=true - Get only completed tasks.

GET /api/tasks?completed=false - Get only pending tasks.

POST /api/tasks: Add a new task.

Validation: Requires a non-empty title in the request body.

PUT /api/tasks/:id: Mark a task as completed or toggle its completion status.

DELETE /api/tasks/:id: Delete a task.

Setup and Installation
Clone the repository (or create the files manually):
If you were provided with a repository, clone it. Otherwise, create a new directory for your project.

mkdir task-manager-backend
cd task-manager-backend

Initialize Node.js project:

npm init -y

This will create a package.json file.

Install dependencies:

npm install express cors

Create app.js:
Create a file named app.js in the root of your project directory and paste the provided backend code into it.

Running the Application
Start the server:
Open your terminal, navigate to your project directory (task-manager-backend), and run:

node app.js

Access the API:
The API will be running on http://localhost:3000 (or the port specified by the PORT environment variable).
You can visit http://localhost:3000 in your browser to see a simple "API is Running" page with endpoint details.

API Endpoints
You can use tools like Postman, Insomnia, or curl to test the API.

Get All Tasks
URL: /api/tasks

Method: GET

Optional Query Parameters:

completed=true: Returns tasks where completed is true.

completed=false: Returns tasks where completed is false.

Response: 200 OK with an array of task objects.

Add a New Task
URL: /api/tasks

Method: POST

Headers: Content-Type: application/json

Body:

{
  "title": "My New Task"
}

Response: 201 Created with the newly created task object.

Error Response: 400 Bad Request if title is missing or empty.

Mark a Task as Completed (or toggle)
URL: /api/tasks/:id (replace :id with the actual task ID)

Method: PUT

Headers: Content-Type: application/json

Body (optional):

{
  "completed": true
}

If completed is provided, it will set the status. If not provided, it will toggle the current status.

Response: 200 OK with the updated task object.

Error Response: 404 Not Found if the task ID does not exist.

Delete a Task
URL: /api/tasks/:id (replace :id with the actual task ID)

Method: DELETE

Response: 204 No Content on successful deletion.

Error Response: 404 Not Found if the task ID does not exist.
