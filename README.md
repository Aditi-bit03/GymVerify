# 💪 GymVerify

**GymVerify** is a full-stack gym membership contact and verification system. It features a Vite + React frontend and a Node.js + Express backend, designed to securely handle contact form submissions and send confirmation emails using Nodemailer.

---

## 🚀 Features

* 🧾 Contact form with real-time validations
* 📬 Email notifications via Nodemailer
* 🔐 Secure environment variable handling with dotenv
* ⚡ Fast build and development using Vite
* 🌐 CORS-enabled backend
* 📁 Clean modular structure for frontend and backend
* ☁️ Easy deployment with Vercel (monorepo setup)

---

## 🛠️ Tech Stack

### Frontend:

* React (via Vite)
* React Router DOM
* Axios
* React Toastify
* React Spinners
* Lucide React Icons

### Backend:

* Node.js
* Express.js
* Nodemailer
* dotenv
* CORS

---

## 📁 Project Structure

```
GymVerify/
├── frontend/        # React app (Vite)
│   ├── src/
│   ├── public/
│   └── vite.config.js
├── backend/         # Node.js API
│   ├── utils/sendEmail.js
│   ├── app.js
│   └── .env
├── vercel.json      # Vercel deployment config
└── README.md
```

---

## ⚙️ Environment Variables

Create a `.env` file in the `backend/` directory with the following keys:

```env
PORT=4000
FRONTEND_URL=http://localhost:5173
EMAIL_USER=your_email@example.com
EMAIL_PASS=your_email_password
```

> ⚠️ Ensure `.env` is added to `.gitignore` and never pushed to version control.

---

## 🧪 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Aditi-bit03/GymVerify.git
cd GymVerify
```

### 2. Install Dependencies

#### Frontend:

```bash
cd frontend
npm install
```

#### Backend:

```bash
cd ../backend
npm install
```

### 3. Run the App Locally

#### Start Frontend (Vite):

```bash
cd ../frontend
npm run dev
```

#### Start Backend (Express):

```bash
cd ../backend
npm run dev
```

---

## 🌐 Deployment (Vercel)

Deployment is configured for Vercel using a monorepo and `vercel.json`:

```json
{
  "version": 2,
  "builds": [
    {
      "src": "backend/app.js",
      "use": "@vercel/node"
    },
    {
      "src": "frontend/index.html",
      "use": "@vercel/static-build"
    }
  ],
  "routes": [
    {
      "src": "/api/(.*)",
      "dest": "backend/app.js"
    },
    {
      "src": "/(.*)",
      "dest": "/frontend/dist/$1"
    }
  ]
}
```

> 🎯 Deploy via Vercel dashboard and add your environment variables under **Project → Settings → Environment Variables**.

---

## 📧 Email Functionality

* The backend exposes a `POST /api/send/mail` endpoint
* Accepts `name`, `email`, and `message`
* Sends an email to the admin using Nodemailer

---

## 🙌 Contributing

Contributions are welcome! Fork the repo, create a branch, and submit a PR.

---

## 📄 License

This project is licensed under the MIT License.

---

## ✨ Author

* [Aditi Priya](https://github.com/Aditi-bit03)
