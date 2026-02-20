# FlaskAuthApp

A minimal Flask authentication demo with registration, login, protected dashboard, and SQLite persistence. Passwords are hashed with bcrypt and stored via SQLAlchemy.

Made for Flask Auth Assignment in my 4th Sem of college.

## Tech Stack
- Python
- Flask
- Flask-SQLAlchemy (SQLite storage)
- bcrypt for password hashing

## Prerequisites
- Python 3.10+ recommended

## Setup
1) Create and activate a virtual environment (Windows PowerShell):
```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```
2) Install dependencies:
```powershell
pip install -r requirements.txt
```
3) Run the app:
```powershell
python app.py
```
4) Visit http://127.0.0.1:5000 in your browser.

## How it works
- On first run, SQLite db `database.db` is created automatically via `db.create_all()` inside `app.py`.
- Registration creates a user with a bcrypt-hashed password.
- Login checks the hash and stores the user email in the session.
- `/dashboard` is protected; it redirects to `/login` if no session.
- `/logout` clears the session and redirects to login.

## Project layout
- app.py — Flask app, models, routes
- templates/ — Jinja2 templates for pages

## Troubleshooting
- If dependencies fail, upgrade pip: `python -m pip install --upgrade pip`.
- If the app cannot bind to the port, stop other processes using 5000 or run `python app.py --port 5001` (after adjusting the code to accept `--port`).
