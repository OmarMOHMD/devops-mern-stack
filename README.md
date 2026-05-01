# 🚀 DevOps MERN Stack - Task Manager

A modern, full-stack web application built with the **MERN stack** (MongoDB, Express, React, Node.js) designed to demonstrate containerization, DevOps practices, and deployment strategies. Perfect for learning how to build, dockerize, and manage microservices in production.

---

## 📋 What's Inside?

This project is a **Task Manager application** that showcases:

- **Frontend** (React + Vite): Lightning-fast single-page application with Tailwind CSS styling
- **Backend** (Express.js + Node.js): RESTful API with MongoDB integration
- **Database** (MongoDB): NoSQL data persistence with Mongoose ORM
- **Containerization** (Docker): Production-ready Docker Compose setup for orchestration

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────┐
│     Browser (React + Vite)              │
│   Running on http://localhost:5174      │
└──────────────────┬──────────────────────┘
                   │ HTTP/REST
                   ↓
┌─────────────────────────────────────────┐
│   Express.js API Server                 │
│   Running on http://localhost:5000      │
│   Routes: GET/POST/DELETE /api/tasks    │
└──────────────────┬──────────────────────┘
                   │ Database Queries
                   ↓
┌─────────────────────────────────────────┐
│   MongoDB                               │
│   Running on mongodb://localhost:27017  │
│   Database: task-app                    │
└─────────────────────────────────────────┘
```

---

## 🎯 Features

✅ **Create Tasks** - Add new tasks with title and description  
✅ **View All Tasks** - Browse all tasks sorted by creation date  
✅ **Delete Tasks** - Remove completed or unwanted tasks  
✅ **Error Handling** - User-friendly error messages and retry logic  
✅ **Responsive Design** - Tailwind CSS for mobile-first UI  
✅ **Docker Support** - Full containerization for easy deployment  

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | React 19, Vite 6, Tailwind CSS 4 |
| **Backend** | Express 4.18, Node.js 20+ |
| **Database** | MongoDB 7.5, Mongoose 7.5 |
| **DevOps** | Docker, Docker Compose |
| **Code Quality** | ESLint 9, Prettier 3 |

---

## 📦 Project Structure

```
devops-mern-stack/
├── client/                    # React Frontend
│   ├── src/
│   │   ├── components/       # Reusable UI components
│   │   ├── services/         # API service layer
│   │   ├── utils/            # Utility functions
│   │   ├── App.jsx           # Main component
│   │   └── main.jsx          # Entry point
│   ├── Dockerfile            # Client container config
│   ├── package.json
│   └── vite.config.js
│
├── server/                    # Express Backend
│   ├── controllers/          # Request handlers
│   ├── models/               # Mongoose schemas
│   ├── routes/               # API endpoints
│   ├── Dockerfile            # Server container config
│   ├── server.js             # Main server file
│   └── package.json
│
├── docker-compose.yml        # Orchestration config
└── README.md                 # This file
```

---

## 🚀 Quick Start

### Prerequisites
- **Node.js** 16+ and **npm**
- **MongoDB** (local or Docker)
- **Docker & Docker Compose** (for containerized setup)

### Option 1: Local Development

```bash
# 1. Install MongoDB (Windows)
# Download from: https://www.mongodb.com/try/download/community
# Or use Docker: docker run -d -p 27017:27017 --name mongodb mongo:latest

# 2. Terminal 1 - Backend
cd server
npm install
npm run dev          # Runs on http://localhost:5000

# 3. Terminal 2 - Frontend
cd client
npm install
npm run dev          # Runs on http://localhost:5174
```

### Option 2: Docker Compose (Production-like)

```bash
# Start all services
docker-compose up --build

# Services available at:
# - Frontend: http://localhost:5173
# - Backend:  http://localhost:5000
# - MongoDB:  localhost:27017
```

### Setup Environment Variables

Create `.env` in the `server/` directory:

```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/task-app
```

Create `.env.local` in the `client/` directory:

```env
VITE_API_URL=http://localhost:5000/api
```

---

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| **GET** | `/api/tasks` | Retrieve all tasks |
| **POST** | `/api/tasks` | Create a new task |
| **DELETE** | `/api/tasks/:id` | Delete a task by ID |
| **GET** | `/health` | Health check endpoint |

### Example: Create a Task

```bash
curl -X POST http://localhost:5000/api/tasks \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Complete DevOps setup",
    "description": "Configure Docker and MongoDB for production"
  }'
```

---

## 🧪 Available Scripts

### Client
```bash
npm run dev          # Start development server
npm run build        # Build for production
npm run preview      # Preview production build
npm run lint         # Lint code
npm run lint:fix     # Auto-fix lint issues
npm run format       # Format with Prettier
```

### Server
```bash
npm run dev          # Start with nodemon (auto-reload)
npm start            # Start production server
npm run lint         # Lint code
npm run lint:fix     # Auto-fix lint issues
npm run format       # Format with Prettier
```

---

## 🐳 Docker Commands

```bash
# Build and start all services
docker-compose up --build

# Start in background
docker-compose up -d

# View logs
docker-compose logs -f

# Stop services
docker-compose down

# Remove volumes (deletes MongoDB data)
docker-compose down -v
```

---

## 🔍 Troubleshooting

| Issue | Solution |
|-------|----------|
| `Failed to fetch tasks` | Ensure backend is running and MongoDB is connected |
| `Port 5000 already in use` | Kill process: `lsof -i :5000` then `kill -9 <PID>` |
| `MongoDB connection refused` | Start MongoDB: `docker run -d -p 27017:27017 mongo:latest` |
| `VITE_API_URL undefined` | Create `.env.local` in client directory with API URL |

---

## 📚 Learning Resources

- [MERN Stack Guide](https://www.mongodb.com/developer/languages/javascript/mern-stack/)
- [Express.js Documentation](https://expressjs.com/)
- [React Documentation](https://react.dev/)
- [Docker Best Practices](https://docs.docker.com/develop/dev-best-practices/)
- [MongoDB University](https://university.mongodb.com/)

---

## 🎓 DevOps Concepts Demonstrated

✨ **Containerization** - Docker images for isolated environments  
✨ **Orchestration** - Docker Compose for multi-container apps  
✨ **Environment Management** - .env files for configuration  
✨ **Service Communication** - Internal networking between containers  
✨ **Data Persistence** - MongoDB volumes in containers  
✨ **Development to Production** - Consistent environments across stages  

---

## 📄 License

MIT License - Free to use for learning and development!

---

## 🤝 Contributing

Feel free to fork, modify, and extend this project for your DevOps learning journey!

---

**Happy Coding! 🎉** Build something awesome with this MERN stack foundation.
