# Full Stack Development - Assignment 3

This repository contains solutions for **Assignment 3** of the Full Stack Web Development course. It covers concepts including Express.js form validation, file uploads via Multer, session management with file-store and Redis, MongoDB role-based authorization, MERN stack application with 2-level category hierarchy, and Sequelize ORM integration with React.

---

## 📁 Repository Directory Structure

```text
Assignment - 3/
├── 76_Shah_Sarthak_701_A3.pdf  # Official Assignment Documentation & Code Submission PDF
├── q1/                         # Form Validation & File Upload (Express + Multer + EJS)
├── q2/                         # File-Based Session Authentication (Express + session-file-store)
├── q3/                         # Redis Session Management (Express + connect-redis)
├── q4/                         # MongoDB Role-Based Auth & Admin Middleware (Express + Mongoose + EJS)
├── q5/                         # Fullstack User Auth App (Express Backend + React Frontend)
├── q6/                         # Fullstack Product Catalog (Express Backend + React Frontend)
├── q7/                         # MERN E-Commerce App (2-Level Category + Cart + Admin Portal)
├── q8/                         # Student Collection CRUD App (Express + Sequelize ORM + React)
├── screenshots/                # Application Screenshots
│   ├── question_7.png
│   └── question_8.png
├── .gitignore                  # Git exclusion config (ignoring node_modules, .env, *.sqlite, etc.)
└── README.md                   # Master Documentation
```

---

## 📄 Submission Documentation

The complete assignment document with detailed explanations, source code snippets, and output verification is available as a PDF in the repository root:
- **PDF File**: [`76_Shah_Sarthak_701_A3.pdf`](./76_Shah_Sarthak_701_A3.pdf)

---

## 🚀 Quick Setup & Installation

All dependencies for both single-folder applications and multi-folder fullstack projects have been pre-verified and installed.

To run any question:

1. **Clone or download** the repository.
2. Navigate into the specific question directory.
3. Install dependencies (if not already installed) using `npm install`.
4. Run the backend/frontend development servers.

---

## 📖 Question Summaries & Code Structure

### 🔹 Question 1: Form Validation & File Uploads
- **Technologies**: Express.js, Multer, `express-validator`, EJS
- **Directory**: [`q1/`](./q1)
- **Key Files**:
  - `app.js`: Express server, Multer disk storage setup (profile pic & multiple pictures upload), `express-validator` middleware rules, file download endpoint `/download/:filename`.
  - `views/register.ejs`: Registration form.
  - `views/result.ejs`: Displaying submitted data and uploaded files with download links.
- **How to Run**:
  ```bash
  cd q1
  npm start
  ```
  Access at `http://localhost:8000`

---

### 🔹 Question 2: File-Based Session Authentication
- **Technologies**: Express.js, `express-session`, `session-file-store`, EJS
- **Directory**: [`q2/`](./q2)
- **Key Files**:
  - `app.js`: Configures session storage using local file store under `./sessions`. Handles login authentication, session verification for `/home` and `/profile`, and session destruction `/logout`.
- **How to Run**:
  ```bash
  cd q2
  npm start
  ```
  Access at `http://localhost:8000/login` (Credentials: `admin` / `1234`)

---

### 🔹 Question 3: Redis Session Management
- **Technologies**: Express.js, Redis, `connect-redis`, `express-session`, EJS
- **Directory**: [`q3/`](./q3)
- **Key Files**:
  - `app.js`: Establishes Redis client connection via `createClient()`, connects `RedisStore` to `express-session`, and manages persistent user sessions.
  - `.env`: Defines `REDIS_URL`.
- **How to Run**:
  ```bash
  # Ensure local Redis server is running
  cd q3
  npm start
  ```
  Access at `http://localhost:8000/login`

---

### 🔹 Question 4: Role-Based Authorization & MongoDB
- **Technologies**: Express.js, MongoDB, Mongoose, EJS, Session Auth
- **Directory**: [`q4/`](./q4)
- **Key Files**:
  - `server.js`: Server setup & database initialization.
  - `config/db.js`: MongoDB Mongoose connection string.
  - `models/User.js`: User schema with role definition (`user`, `admin`).
  - `middlewares/auth.js`: Authorization middlewares checking user session and admin privileges.
  - `routes/AuthRoutes.js` & `routes/AdminRoutes.js`: Protected routes for user home and admin control panel.
- **How to Run**:
  ```bash
  # Ensure MongoDB service is running on mongodb://127.0.0.1:27017
  cd q4
  npm start
  ```
  Access at `http://localhost:8000`

---

### 🔹 Question 5: Fullstack User Management App
- **Technologies**: Express.js Backend + React Frontend
- **Directory**: [`q5/`](./q5)
- **Structure**:
  - `q5/backend/`: Express API server providing user management endpoints.
  - `q5/frontend/`: React client application communicating with backend.
- **How to Run**:
  ```bash
  # Terminal 1 (Backend)
  cd q5/backend
  npm start

  # Terminal 2 (Frontend)
  cd q5/frontend
  npm run dev
  ```

---

### 🔹 Question 6: Fullstack Product Catalog App
- **Technologies**: Express.js Backend + React Frontend
- **Directory**: [`q6/`](./q6)
- **Structure**:
  - `q6/backend/`: Express API handling product collection routes.
  - `q6/frontend/`: React Vite application displaying interactive product catalog.
- **How to Run**:
  ```bash
  # Terminal 1 (Backend)
  cd q6/backend
  npm run dev

  # Terminal 2 (Frontend)
  cd q6/frontend
  npm run dev
  ```

---

### 🔹 Question 7: MERN E-Commerce App with 2-Level Category & Cart
- **Technologies**: MongoDB, Express.js, React.js, Node.js (MERN)
- **Directory**: [`q7/`](./q7)
- **Features**:
  1. **2-Level Category Hierarchy**:
     - Level 1: Main Categories (e.g., Electronics, Fashion)
     - Level 2: Sub-Categories (e.g., Smartphones under Electronics)
  2. **Admin Dashboard**: Create/Delete Main and Sub Categories, Add/Manage Products, View User Orders.
  3. **User Store**: Filter products dynamically by Main & Sub Category, add items to Shopping Cart drawer, view subtotal, and place orders.
- **How to Run**:
  ```bash
  # Ensure MongoDB daemon is active on port 27017

  # Terminal 1 (Backend Server)
  cd q7/server
  npm start

  # Terminal 2 (Frontend Client)
  cd q7/client
  npm run dev
  ```
  Access frontend at `http://localhost:3000`

---

### 🔹 Question 8: Student Collection CRUD using Sequelize ORM
- **Technologies**: Express.js, Sequelize ORM (SQLite / MySQL), React.js
- **Directory**: [`q8/`](./q8)
- **Features**:
  - **Sequelize Model**: `Student` schema (`id`, `name`, `rollNo`, `email`, `course`, `age`) with field-level validations.
  - **REST API Endpoints**: `GET`, `POST`, `PUT`, `DELETE` operations on student collection.
  - **React UI**: Simple, clean humanoid student project interface with Add/Edit form, live search filter table, and interactive delete confirmation.
- **How to Run**:
  ```bash
  # Terminal 1 (Backend - Port 5000)
  cd q8/backend
  npm start

  # Terminal 2 (Frontend - Port 3001)
  cd q8/frontend
  npm run dev
  ```
  Access frontend at `http://localhost:3001`

---

