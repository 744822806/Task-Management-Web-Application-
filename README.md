Task Management Web Application (Node.js · Express · MongoDB · JWT)

A full-stack task management application featuring secure user authentication, per-user task ownership, and a lightweight HTML/JavaScript frontend.
This project demonstrates backend API design, authentication workflows, database modeling, and frontend–backend integration.

🚀 Features
🔐 Authentication

User registration and login

Secure password hashing (bcrypt)

JWT-based authentication for sessionless security

Protected routes with authorization middleware

📝 Task Management

Create, read, update, and delete tasks

Each task is owned by the authenticated user

Prevents cross-user data access

Real-time UI updates via frontend API calls

🌐 Frontend

Simple and clean HTML/CSS/JS interface

Login, register, and task creation UI

Fetch-based API communication

Auto-refreshing task list

🗄 Database

MongoDB + Mongoose

User schema with hashed credentials

Task schema linked to user via owner field

📁 Project Structure
/
├── src/
│   ├── app.js                 # Express server + routing + MongoDB connection
│   ├── middleware/
│   │   └── auth.js            # JWT authentication middleware
│   ├── models/
│   │   ├── User.js            # User schema
│   │   └── Task.js            # Task schema (per-user)
│   └── routes/
│       ├── auth.js            # /auth/register, /auth/login
│       └── tasks.js           # /tasks CRUD API
│
├── public/
│   ├── index.html             # Frontend UI
│   └── script.js              # Frontend logic (fetch API calls)
│
└── README.md

🔌 API Endpoints
Authentication
Method	Endpoint	Description
POST	/auth/register	Create new user
POST	/auth/login	Returns JWT token
Task Routes (Protected by JWT)
Method	Endpoint	Description
GET	/tasks	Get all tasks for logged-in user
POST	/tasks	Create a new task
PUT	/tasks/:id	Update a task
DELETE	/tasks/:id	Delete a task

Include JWT token in header:

Authorization: Bearer <token>

🛠 Setup & Installation
1. Install dependencies
npm install

2. Configure MongoDB

Edit src/app.js:

mongoose.connect("YOUR_MONGO_URI_HERE");

3. Start backend
node src/app.js


Server runs at:

http://localhost:4000

4. Open frontend

Open:

public/index.html


The frontend communicates with the backend via Fetch API.

🧪 How to Use

Register a new account

Log in to receive a JWT token

Add new tasks

Click on a task to delete it

Tasks are saved per user and cannot be accessed by other accounts

🚀 Future Improvements

Task pagination & search

React or Vue frontend

User profile management

Docker containerization

Render/AWS deployment

Role-based access control (RBAC)
