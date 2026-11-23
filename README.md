# swapr — SkillSwap Platform

A full-stack skill-sharing marketplace where users can list their skills, discover others, and swap expertise in real-time. Built with a modern JavaScript stack featuring real-time messaging, secure authentication, and a clean responsive UI.

---

## ✨ Features

- **Authentication** — Email/password + Google OAuth (Passport.js + JWT)
- **Skill Marketplace** — Browse, search, and filter skills by category
- **Skill Swaps** — Request, accept, and manage skill exchanges
- **User Profiles** — Showcase skills, experience, and reviews
- **Reviews & Ratings** — Build trust through peer feedback
- **Real-time Messaging** — Socket.IO-powered chat for swap coordination (Phase 2)
- **Image Uploads** — Cloudinary integration for profile/skill images

---

## 🛠️ Tech Stack

| Layer | Technologies |
|-------|--------------|
| **Frontend** | Next.js 14, React 18, Tailwind CSS, Socket.IO Client |
| **Backend** | Node.js, Express, MongoDB + Mongoose |
| **Auth** | Passport.js (Local + Google OAuth), JWT |
| **Real-time** | Socket.IO |
| **Media** | Cloudinary |
| **Deployment** | Netlify (frontend), Render/railway (backend) |

---

## 📁 Project Structure

```
swapr/
├── frontend/          # Next.js application
│   ├── src/
│   │   ├── app/       # App Router pages
│   │   ├── components/
│   │   ├── hooks/
│   │   └── lib/
│   ├── public/
│   └── ...
├── backend/           # Express API
│   ├── src/
│   │   ├── controllers/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── middleware/
│   │   └── utils/
│   ├── server.js
│   └── ...
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- MongoDB (local or Atlas)
- Google Cloud Console project (for OAuth)
- Cloudinary account (for image uploads)

### Backend Setup

```bash
cd backend
npm install

# Create .env file
cp .env.example .env
# Edit .env with your credentials

npm run dev
# Server runs on http://localhost:5000
```

**Environment Variables:**

```env
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_super_secret_jwt_key
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
BASE_URL=http://localhost:5000
```

### Frontend Setup

```bash
cd frontend
npm install

# Create .env.local
echo "NEXT_PUBLIC_API_URL=http://localhost:5000" > .env.local

npm run dev
# App runs on http://localhost:3000
```

---

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/auth/signup` | Register new user |
| `POST` | `/api/auth/login` | Login user |
| `GET` | `/api/auth/google` | Initiate Google OAuth |
| `GET` | `/api/auth/me` | Get current user |
| `GET` | `/api/skills` | List all skills (with filters) |
| `POST` | `/api/skills` | Create a skill listing |
| `GET` | `/api/skills/:id` | Get skill details |
| `POST` | `/api/swaps` | Request a skill swap |
| `PATCH` | `/api/swaps/:id` | Update swap status |
| `GET` | `/api/users/:id` | Get user profile |
| `POST` | `/api/reviews` | Submit a review |

---

## 🔐 Authentication Flow

1. User signs up/logs in via email/password or Google OAuth
2. Server issues JWT access token + refresh token
3. Tokens stored in HttpOnly cookies
4. Protected routes validate JWT via middleware
5. Socket.IO connections authenticated via token

---

## 🎯 Roadmap

- [ ] Real-time notifications
- [ ] Video call integration for swaps
- [ ] Skill categories & tagging system
- [ ] Advanced search with filters
- [ ] Mobile-responsive improvements
- [ ] Unit & integration tests

---

## 📄 License

MIT License — feel free to use and modify.

---

## 👨‍💻 Author

**Dinesh Reddy Pothula**  
[GitHub](https://github.com/dineshreddypothula) • [LinkedIn](https://www.linkedin.com/in/dinesh-reddy-pothula/)