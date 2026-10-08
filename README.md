# Multi-Agent Marketplace

A full-stack marketplace platform where users can discover, publish, test, and compose AI agents into workflows, with built-in billing, wallets, reviews, and admin tools.

## Features

- **Agent Marketplace**: browse, search, filter by category and tag, and view agent details
- **Agent Playground**: test agents live before using them
- **Publish Agents**: versioned agents with pricing, tags, and categories
- **Workflow Builder**: chain multiple agents into multi-step workflows
- **Billing**: wallet, transactions, invoices, subscriptions, and usage-based pricing
- **Reviews and Ratings**: user feedback on agents
- **Security**: JWT auth, RBAC, API keys, rate limiting, sandboxing, and audit logs
- **Admin Panel**: manage users, agents, transactions, and platform analytics

## Tech Stack

| Layer      | Technology                                   |
|------------|----------------------------------------------|
| Backend    | Python, FastAPI, SQLAlchemy, Alembic         |
| AI         | Google Gemini API                            |
| Frontend   | React (Vite), Tailwind CSS, Redux, Axios     |
| Database   | PostgreSQL                                   |
| Deployment | Docker, Docker Compose, Nginx                |

## Project Structure

```
multi-agent-marketplace/
├── backend/       # FastAPI app (models, schemas, routers, services, agents, billing, security)
├── frontend/      # React + Vite app
├── database/      # SQL schema, seeds, migrations
├── docs/          # Architecture, API, security, billing docs
└── deployment/    # Nginx config and production Dockerfiles
```

## Getting Started

### Prerequisites

- Python 3.10+
- Node.js 18+
- PostgreSQL 14+
- Docker (optional)

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd multi-agent-marketplace
```

### 2. Backend setup

```bash
cd backend
python -m venv venv
venv\Scripts\activate          # Windows
# source venv/bin/activate     # macOS/Linux

pip install -r requirements.txt
copy .env.example .env         # Windows (cp on macOS/Linux)
```

Edit `backend/.env` and set your values:

```env
DATABASE_URL=postgresql://user:password@localhost:5432/marketplace
SECRET_KEY=your-secret-key
GEMINI_API_KEY=your-gemini-api-key
```

Run migrations and start the server:

```bash
alembic upgrade head
python run.py
```

Backend runs at `http://localhost:8000`, with API docs at `http://localhost:8000/docs`.

### 3. Frontend setup

```bash
cd frontend
npm install
copy .env.example .env         # Windows (cp on macOS/Linux)
npm run dev
```

Frontend runs at `http://localhost:5173`.

### 4. Run with Docker

```bash
docker-compose up --build
```

## Testing

```bash
cd backend
pytest
```

## Documentation

- [Architecture](docs/ARCHITECTURE.md)
- [API Documentation](docs/API_DOCUMENTATION.md)
- [Database Schema](docs/DATABASE_SCHEMA.md)
- [Setup Guide](docs/SETUP_GUIDE.md)
- [User Flows](docs/USER_FLOWS.md)
- [Security](docs/SECURITY.md)
- [Billing Model](docs/BILLING_MODEL.md)

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m "Add your feature"`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

## License

This project is licensed under the terms of the [LICENSE](LICENSE) file.