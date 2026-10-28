# NursingPro API

Backend API for **NursingPro**, a mobile app that helps users prepare for nursing competitive exams with mock tests and course content.

## Tech Stack

- **FastAPI** — REST API framework
- **PostgreSQL** + **SQLAlchemy** — data persistence
- **Alembic** — database migrations
- **python-jose / passlib / bcrypt** — JWT authentication & password hashing
- **Pydantic** — request/response validation
- **Docker** — containerized deployment

## Project Structure

```
app/
├── api/        # route handlers
├── core/       # settings, config
├── crud/       # database operations
├── db/         # session/engine setup
├── models/     # SQLAlchemy models
├── schemas/    # Pydantic schemas
├── security.py # JWT + password hashing
└── main.py     # app entrypoint
```

## Getting Started

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# configure your database connection, then run migrations
alembic upgrade head

uvicorn app.main:app --reload
```

Or with Docker:

```bash
docker build -t nursingpro-api .
docker run -p 8000:8000 nursingpro-api
```

## License

MIT
