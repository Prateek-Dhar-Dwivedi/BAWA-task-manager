# MERN Task Manager

A simple to-do application built using the **MERN stack**—MongoDB, Express.js, React, and Node.js. Learn full-stack development with basic functionality to **Add**, **View**, **Update**, and **Delete** tasks.

## 🔗 Live Demo

* **Frontend (UI):** [https://bawa-task-manager.vercel.app/]([https://bawa-task-manager.vercel.app/])
* **Backend (API):** [https://bawa-task-manager.onrender.com]([https://bawa-task-manager.onrender.com])

---

## 📂 What’s Inside?

-   **Backend** (`backend/`): REST API using Node.js, Express.js, and MongoDB to manage tasks.
-   **Frontend** (`frontend/`): React app (via Vite) that lets you interact with tasks in a modern UI.
-   **Tailwind CSS** already integrated for quick and clean styling.

---

## 🚀 Setup Guide (Local Development)

### 1. Clone the repository

```bash
https://github.com/Prateek-Dhar-Dwivedi/BAWA-task-manager
cd mern-task-manager

```

### 2. Setup the Backend (API server)

```bash
cd backend
npm install

```

1. Create a `.env` file in the `backend/` folder and add your MongoDB connection string:
```env
MONGO_URI=your_mongodb_connection_string

```


2. Start the backend server:
```bash
node server.js

```


*It should run on `http://localhost:5000`.*

### 3. Setup the Frontend (User interface)

Open a new terminal window:

```bash
cd ../frontend
npm install
npm run dev -- --host

```

* This starts the app at `http://localhost:5173`.
* Use `--host` so it works even on other devices on the same network.

### 4. Use the App

* Open the app in your browser.
* Add tasks in the input field.
* Click on a task to mark it complete (strikethrough).
* Use the delete option to remove a task.


### For deployment of backed on Render:
You must have to add the .env variables, Scroll down to **Environment Variables** and add:
* `MONGO_URI`: Your MongoDB connection string.
* `PORT`: `10000` (Render's default port).
---
## 💡 Why It’s Helpful for Beginners

* Clear separation of **frontend** and **backend** code.
* Learn how React interacts with a **REST API**.
* Explore essential web development skills: routing, CRUD, state management, styling.
* Lightweight and easy to run—no heavy setup required.

---

## 🛠 Tips if It Doesn’t Work

* **Backend First:** Make sure the backend is running before using the frontend.
* **Connection Issues:** If tasks don’t load:
* **Locally:** Ensure the `api.js` in `frontend/src` points to `http://localhost:5000` (or your LAN IP).
* **On Render:** Ensure you added the `VITE_API_URL` environment variable correctly.


* **Windows Users:** If you see line-ending warnings from Git (`LF will be replaced by CRLF`), that’s normal and safe to ignore.

---

## Happy Coding!

Build, break, fix, and learn—this app is your sandbox to explore full-stack development with MERN. Feel free to tweak it, experiment, and make it your own!
