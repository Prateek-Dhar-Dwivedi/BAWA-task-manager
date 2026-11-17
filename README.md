# MERN Task Manager

A simple to-do application built using the **MERN stack**—MongoDB, Express.js, React, and Node.js. Learn full-stack development with basic functionality to **Add**, **View**, **Update**, and **Delete** tasks.

## 🔗 Live Demo

* **Frontend (UI):** [https://mern-task-frontend-gwue.onrender.com/](https://mern-task-frontend-gwue.onrender.com/)
* **Backend (API):** [https://mern-task-manager-b89p.onrender.com/](https://mern-task-manager-b89p.onrender.com/)

---

## 📂 What’s Inside?

-   **Backend** (`backend/`): REST API using Node.js, Express.js, and MongoDB to manage tasks.
-   **Frontend** (`frontend/`): React app (via Vite) that lets you interact with tasks in a modern UI.
-   **Tailwind CSS** already integrated for quick and clean styling.

---

## 🚀 Setup Guide (Local Development)

### 1. Clone the repository

```bash
[(https://github.com/Prateek-Dhar-Dwivedi/BAWA-task-manager)](https://github.com/Prateek-Dhar-Dwivedi/BAWA-task-manager)
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

---

## ☁️ Deployment Guide (Render)

Deploy your app for free using Render. You will create two separate services: one for the backend and one for the frontend.

### Step 1: Deploy the Backend (Web Service)

1. Log in to [Render](https://render.com/).
2. Click **New +** and select **Web Service**.
3. Connect your GitHub repository.
4. Configure the service:
* **Name:** `mern-task-backend`
* **Root Directory:** `backend`
* **Environment:** Node
* **Build Command:** `npm install`
* **Start Command:** `node server.js`


5. Scroll down to **Environment Variables** and add:
* `MONGO_URI`: Your MongoDB connection string.
* `PORT`: `10000` (Render's default port).


6. Click **Create Web Service**.
7. **Copy the URL** provided by Render (e.g., `https://your-backend.onrender.com`). You will need this for the frontend.

### Step 2: Deploy the Frontend (Static Site)

1. Go back to the Render Dashboard.
2. Click **New +** and select **Static Site**.
3. Connect the same GitHub repository.
4. Configure the service:
* **Name:** `mern-task-frontend`
* **Root Directory:** `frontend`
* **Build Command:** `npm install && npm run build`
* **Publish Directory:** `dist`


5. **Environment Variables:**
* Add a variable named `VITE_API_URL`.
* Set the value to your **Backend URL** from Step 1 (e.g., `https://your-backend.onrender.com/api`).


6. **Rewrite Rules:**
* To ensure React Router works correctly, go to the **Redirects/Rewrites** tab.
* Add a new rule:
* **Source:** `/*`
* **Destination:** `/index.html`
* **Action:** Rewrite




7. Click **Create Static Site**.

---

## 🌐 Alternative: Deploy Frontend to GitHub Pages

If you prefer to host the frontend on GitHub Pages instead of Render, follow these steps.

### 1. Install `gh-pages`

In your `frontend/` directory:

```bash
npm install gh-pages --save-dev

```

### 2. Update `vite.config.js`

Add the `base` path property:

```javascript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

// [https://vitejs.dev/config/](https://vitejs.dev/config/)
export default defineConfig({
  plugins: [react()],
  base: "/mern-task-manager/", // REPLACE "mern-task-manager" with your repo name
})

```

### 3. Update `package.json`

In `frontend/package.json`, add the `homepage` and scripts:

```json
{
  "name": "frontend",
  "homepage": "https://<your-github-username>.github.io/mern-task-manager", 
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "predeploy": "npm run build",
    "deploy": "gh-pages -d dist" 
  }
}

```

### 4. Deploy

```bash
npm run deploy

```

### ⚠️ Crucial: Backend Connection for GitHub Pages

Since your frontend is on GitHub Pages but backend is on Render:

1. **Frontend API URL:** Ensure your `api.js` points to the Render Backend URL.
2. **Backend CORS:** Update `backend/server.js` to allow the GitHub Pages URL:
```javascript
app.use(cors({
  origin: ["[https://lovnishverma.github.io](https://lovnishverma.github.io)", "http://localhost:5173"] 
}));

```



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
