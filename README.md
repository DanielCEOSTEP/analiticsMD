# analiticsMD

This repository provides tools for collecting Telegram messages and storing them in a database.

## Installing dependencies

Use a Python 3 virtual environment and install requirements:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

## Environment variables

Before running the collector, set these variables:

- `TELEGRAM_API_ID` and `TELEGRAM_API_HASH` – Telegram API credentials.
- `TELEGRAM_BOT_TOKEN` – bot token used to access chats.
- `DATABASE_URL` – connection string for your database.

Export them in your shell or place them in an `.env` file.

## Database setup

Create a database and initialize tables. Examples for common engines:

**PostgreSQL**

```bash
createdb analiticsmd
```

**SQLite**

```bash
sqlite3 analiticsmd.db < /dev/null
```

Then run the initialization helper:

```bash
python scripts/init_db.py
```

## Running the Telegram collector

With dependencies installed and the database configured, start the collection script:

```bash
python scripts/collect_telegram.py
```

The script pulls messages from Telegram and stores them in the configured database.
