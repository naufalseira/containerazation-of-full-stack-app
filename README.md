# Docker Compose Configuration
This repository contains a Docker Compose setup for running a full-stack application with frontend, backend, database, and development tools.

## Services
### Frontend
- Built with React/Vite
- Run on port 5173
- Connected to app-network
### Backend
- Built with NestJS
- Auto-migrations run on startup
- Run on port 8000
- Connected to app-network and db-network
### Database (PostgreSQL)
- Latest PostgreSQL version
- Persistent data storage
- Run on port 5432
- Connected to db-network
### pgAdmin
- Latest pgAdmin version
- Web-based PostgreSQL admin interface
- Run on port 5050
- Connected to db-network
### Prisma Studio
- Database management UI
- Run on port 5555
- Connected to db-network

## Networks
- app-network: Connects frontend and backend
- db-network: Connects backend and database services

## Volumes
- postgres_data: Persistent database storage
- pgadmin_data: Persistent pgAdmin configuration

## Getting Started
1. Make sure you have Docker and Docker Compose installed
2. Clone the repository
3. Create .env files from the examples:
```bash
cp frontend/.env.example frontend/.env
cp backend/.env.example backend/.env
```
4. Start the services:
```bash
docker compose up --build -d
```

## Available Endpoints
- Frontend: http://localhost:5173
- Backend API: http://localhost:8000
- pgAdmin: http://localhost:5050
- Prisma Studio: http://localhost:5555