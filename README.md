# Roast Café (Full Stack)

A full-stack web app with an Express (Jade/Pug) backend + a React frontend. Includes pages/routes for the café and reviews, with MongoDB (Mongoose) used for data storage.

---

## Tech stack (languages + software)

### Backend
- **Node.js**
- **Express** (server + routing)
- **Jade/Pug** (server-side rendered views)
- **MongoDB** via **Mongoose**
- **JavaScript** (backend)
- **express-session**, **cookie-parser** (session/cookies)
- **CORS**

### Frontend
- **React** (JavaScript)
- **Create React App** (`react-scripts`)
- **JavaScript** (frontend)
- **Fetch API** (calls backend `/api/...`)

---

## How the frontend talks to the backend

The React app calls:
- `GET /api/hello` (from `roast-frontend/src/App.js`)

The Express app serves this route:
- `app.get('/api/hello', ...)` in `app.js`

> Both apps run on **port 3000** by default, so you typically run either:
> - backend at `http://localhost:3000` and frontend via CRA at another port, **or**
> - change one side’s port using `PORT`.

---

## Prerequisites

- Node.js installed
- MongoDB running locally (the backend uses `mongodb://localhost:27017/roast` in `app_server/models/db.js`)

---

## Start the project

### 1) Backend (Express + MongoDB)


cd Roast-7
npm install
npm run start


Backend runs on `PORT` (default: `3000`).

To verify:
- Open `http://localhost:3000/api/hello`

### 2) Frontend (React)

In a second terminal:


cd roast-frontend
npm install
npm start


CRA will open the React app in the browser.

---

## Migration / setup notes (database)

This project uses **MongoDB + Mongoose**.

- Database name: **`roast`**
- Connection string used in code: `mongodb://localhost:27017/roast`
- Models are in `app_server/models/` (e.g. `review`, plus others like `location` and `users`).

If you need a different MongoDB URL, update `app_server/models/db.js` (or add env-based configuration).

---

## Build for production

### Backend

# If you want production mode, you can run the server normally
npm start


### Frontend

cd roast-frontend
npm run build


---

## Terminal controls

- Stop a running dev server: **Ctrl + C**
- CRA dev server hot-reloads when you change frontend code
- If ports conflict (both default to 3000):
  - set a different `PORT` for one side, e.g.


# Backend
cd Roast-7
PORT=4000 npm run start

# Frontend (CRA)
cd roast-frontend
PORT=3001 npm start


