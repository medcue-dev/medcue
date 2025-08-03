# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

MedCue is a HIPAA and SOC 2 compliant medicine tracking application that helps patients manage medication intake timings with secure alerts and reminders.

**Technology Stack:**
- Backend: Python + FastAPI
- Database: PostgreSQL with encryption
- Frontend: React/Next.js (web) + React Native (mobile)
- Infrastructure: Google Cloud Platform (GCP)

## Project Structure

```
medcue/
├── docs/                    # Project documentation
├── backend/                 # FastAPI backend
└── frontend/                # React/Next.js frontend
```

## Development Setup

*To be added once build system is established*

## Commands

### Full Stack Development (Recommended)
```bash
# Quick start complete environment
./scripts/dev-start.sh

# Stop environment
./scripts/dev-stop.sh

# View logs
./scripts/dev-logs.sh [service] -f

# Reset environment completely
./scripts/dev-reset.sh

# Access services
# Frontend: http://localhost:3000
# Backend:  http://localhost:8000
# API Docs: http://localhost:8000/docs
```

### Backend Development (Standalone)
```bash
# Setup and start backend only
cd backend
./scripts/start.sh

# Docker development
docker compose up backend postgres redis

# Run migrations
docker compose run --rm migrations
# Or: alembic upgrade head

# Create new migration
alembic revision --autogenerate -m "description"

# Run tests (when implemented)
pytest

# Lint and format
black app/
flake8 app/
mypy app/
```

### Frontend Development (Standalone)
```bash
# Setup and start frontend
cd frontend
npm install
npm run dev

# Docker development
docker compose up frontend

# Build for production
npm run build

# Run tests
npm test
npm run test:coverage

# Lint and type check
npm run lint
npm run type-check
```

### Development Tools
```bash
# Database management (pgAdmin)
docker compose --profile tools up -d pgadmin
# Access: http://localhost:5050

# Redis management
docker compose --profile tools up -d redis-commander
# Access: http://localhost:8081

# Email testing (Mailhog)
docker compose --profile tools up -d mailhog
# Access: http://localhost:8025
```

## Architecture

See `docs/architecture.md` for detailed system architecture and security considerations.

## Security Requirements

- All PHI must be encrypted at field level
- HIPAA compliance mandatory for all data handling
- Audit logging required for all user actions
- Multi-factor authentication required

## Notes

- Security-first development approach
- Extensible user system (patients now, caregivers/providers later)
- Offline capability required for mobile app