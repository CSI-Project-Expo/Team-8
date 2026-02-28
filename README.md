# 🎫 Offline Event Registration System

A full-stack web application for managing event registrations with a slot-based system, built using **React** and **Express + MongoDB**.

---

## ✨ Features

- **Event Registration** — Users can register for events by providing their name, USN, branch, semester, section, email, phone, event category, and event title.
- **Slot Management** — Automatic slot tracking with a configurable max capacity (default: 50 slots).
- **Duplicate Prevention** — Prevents duplicate registrations by email or USN.
- **Admin Dashboard** — A protected admin panel to view all registrations, see remaining slots, delete entries, and export data to Excel.
- **Excel Export** — Admins can export registration data as `.xlsx` files.
- **Toast Notifications** — Real-time feedback for all user and admin actions.
- **Responsive Design** — Works across desktop and mobile devices.

---

## 🛠️ Tech Stack

| Layer      | Technology                             |
|------------|----------------------------------------|
| Frontend   | React 19, React Router, React Toastify |
| Backend    | Express.js, Mongoose, CORS, dotenv     |
| Database   | MongoDB Atlas                          |
| Deployment | Vercel (serverless)                    |

---

## 📁 Project Structure

```
offline_event_registration/
├── backend/
│   ├── models/
│   │   └── Registration.js     # Mongoose schema for registrations
│   ├── routes/
│   │   ├── auth.js             # POST /api/register
│   │   └── admin.js            # GET /api/admin-data, DELETE /api/delete/:id
│   ├── server.js               # Express app setup & MongoDB connection
│   ├── vercel.json             # Vercel deployment config
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── App.js              # Main app with registration form & routing
│   │   ├── Admin.js            # Admin dashboard component
│   │   ├── App.css             # Application styles
│   │   └── index.js            # React entry point
│   └── package.json
├── .gitignore
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18+)
- [MongoDB Atlas](https://www.mongodb.com/atlas) account (or a local MongoDB instance)

### 1. Clone the repository

```bash
git clone https://github.com/CSI-Project-Expo/Team-8.git
cd Team-8
```

### 2. Setup the Backend

```bash
cd backend
npm install
```

Create a `.env` file in the `backend/` directory:

```env
MONGO_URI=your_mongodb_connection_string
ADMIN_SECRET=your_admin_secret_key
FRONTEND_URL=http://localhost:3000
PORT=5000
```

Start the backend server:

```bash
npm run dev
```

### 3. Setup the Frontend

```bash
cd frontend
npm install
npm start
```

The app will be running at `http://localhost:3000`.

---

## 📡 API Endpoints

| Method   | Endpoint            | Description                 | Auth               |
|----------|---------------------|-----------------------------|---------------------|
| `POST`   | `/api/register`     | Register for an event       | None                |
| `GET`    | `/api/admin-data`   | Get all registrations       | `x-admin-secret` header |
| `DELETE` | `/api/delete/:id`   | Delete a registration       | `x-admin-secret` header |

---

## 👥 Team 8

Built as part of the **CSI Project Expo**.
## Team Members

- [Shravya S] NNM24IS229
- [Shravya ] NNM24IS226
[Shika Acharya] NNM24IS219
---

## 📄 License

This project is for educational purposes as part of the CSI Project Expo.
