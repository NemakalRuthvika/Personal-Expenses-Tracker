# Spendly — Personal Expense Tracker


A responsive monthly spending dashboard built with Flask, MongoDB, HTML/CSS, vanilla JavaScript, and Chart.js.

## Features

- Add, edit, and delete expenses
- Filter by text, category, and month
- Monthly totals, daily average, budget progress, and month-over-month comparison
- Interactive spending and category charts
- CSV export, dark mode, responsive mobile layout
- MongoDB persistence with automatic demo mode when MongoDB is unavailable
- REST API validation, tests, and GitHub Actions

## Run locally

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
copy .env.example .env
python app.py
```

Open `http://127.0.0.1:5000`. Start MongoDB locally or set `MONGO_URI` to a MongoDB Atlas connection string. Without MongoDB, the app starts in demo mode with sample data.

## Deploy to Render

This repository includes a ready-to-use [`render.yaml`](render.yaml) Blueprint.

1. Click **Deploy to Render** above and connect the repository.
2. Set `MONGO_URI` to your MongoDB Atlas connection string.
3. Create the web service. Render installs the dependencies, starts Gunicorn, and checks `/health`.

The application also runs in demo mode if a local MongoDB service is unavailable.

## Tests

Every push and pull request to `main` runs the test suite and syntax checks through GitHub Actions. Run the same checks locally with:

```bash
python -m pytest --verbose
python -m compileall -q app.py tests
```

## API

| Method | Endpoint | Purpose |
| --- | --- | --- |
| GET, POST | `/api/expenses` | List or create expenses |
| PUT, DELETE | `/api/expenses/<id>` | Update or remove an expense |
| GET | `/api/export` | Download expenses as CSV |
| GET | `/health` | Application health check |
"# Personal-Expenses-Tracker" 
