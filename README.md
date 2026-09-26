# OfficeFlow

OfficeFlow is a lightweight office productivity application designed to centralize everyday work management in one place.

## Current MVP

- Task management
- Task status tracking
- Priority levels
- Due dates
- SQLite persistence
- REST API
- Simple browser dashboard
- Health check endpoint
- Clean project structure for future expansion

## Technology

- Python 3.11+
- FastAPI
- Uvicorn
- SQLite
- SQLAlchemy
- Jinja2

## Project Structure

```
OfficeFlow/
├── app/
│   ├── __init__.py
│   ├── main.py
│   ├── database.py
│   ├── models.py
│   ├── schemas.py
│   └── templates/
│       └── index.html
├── requirements.txt
├── .gitignore
└── README.md
```

## Installation

1. Clone the repository.
2. Create a virtual environment:

```bash
python -m venv .venv
```

3. Activate it.

Windows:

```powershell
.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source .venv/bin/activate
```

4. Install dependencies:

```bash
pip install -r requirements.txt
```

5. Start the application:

```bash
uvicorn app.main:app --reload
```

6. Open the dashboard at:

```
http://127.0.0.1:8000
```

API documentation is available at:

```
http://127.0.0.1:8000/docs
```

## API

### List tasks

`GET /api/tasks`

### Create a task

`POST /api/tasks`

Example:

```json
{
  "title": "Prepare monthly report",
  "description": "Finalize the finance report for management.",
  "priority": "high",
  "due_date": "2026-09-30"
}
```

### Update task status

`PATCH /api/tasks/{task_id}/status`

Example:

```json
{
  "status": "completed"
}
```

### Delete a task

`DELETE /api/tasks/{task_id}`

## Design Principles

OfficeFlow is intentionally modular. The task module is the first foundation and can later be expanded with:

- Employee and team management
- Calendar and reminders
- Document templates
- Expense tracking
- Attendance
- Meeting notes
- Approval workflows
- Reporting and analytics
- Role-based access control
- Authentication
- AI-assisted office automation

## Security

This MVP is intended for local development. Before production deployment, add authentication, authorization, input validation policies, secure secret management, HTTPS, database backups, audit logging, and production database configuration.

## License

MIT
