# Setup & Installation

## Prerequisites
- Node.js 18+
- Python 3.10+
- Docker & Docker Compose
- FFmpeg
- Git

## Quick Start

### 1. Clone Repository
```bash
git clone https://github.com/uniteetech/UNITEEAI.git
cd UNITEEAI
```

### 2. Environment Setup
```bash
# Copy example env
cp .env.example .env

# Edit .env with your API keys
# - OpenAI API key
# - Database credentials
# - AWS/Storage credentials (optional)
```

### 3. Start Services
```bash
# Using Docker Compose (recommended)
docker-compose up -d

# OR manual setup
# Backend
cd backend && pip install -r requirements.txt && python main.py

# Frontend (new terminal)
cd frontend && npm install && npm run dev
```

### 4. Access Application
- Frontend: http://localhost:3000
- API Docs: http://localhost:8000/docs
- Database UI: http://localhost:5432

## Development Workflow

### Running Tests
```bash
# Backend tests
cd backend && pytest

# Frontend tests
cd frontend && npm test
```

### Database Migrations
```bash
cd backend && alembic upgrade head
```

## Troubleshooting
- **Port conflicts:** Modify docker-compose.yml ports
- **GPU access:** Install CUDA and nvidia-docker
- **Memory issues:** Increase Docker memory allocation
