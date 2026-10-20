VIANOVA PUBLIC BETA STARTER

Contains Flask app, responsive templates, CSS, requirements, and Render blueprint.
Features: account registration/login, hashed passwords, posts, image/video upload, likes, comments, basic profile and profile photo, health check, SQLite local fallback and PostgreSQL support via DATABASE_URL.

IMPORTANT HOSTING NOTES:
- Use PostgreSQL for hosted user data and set DATABASE_URL.
- Render free web services use ephemeral local storage. Uploaded media saved locally may disappear after restart/redeploy. Configure durable object storage or a persistent disk before promising reliable public uploads.
- This is an early beta starter, not a finished TikTok-scale platform. DMs, live streaming, notifications, followers, password reset/email verification, reporting/moderation, CSRF protection, rate limiting, terms/privacy pages, backups and durable media hosting still need work.
- Never commit secrets to GitHub. Render should generate VIANOVA_SECRET_KEY. Use HTTPS and set COOKIE_SECURE=1 in production.

LOCAL TEST:
Install Flask, run app.py, open http://127.0.0.1:5000. SQLite is used if DATABASE_URL is unset.

RENDER:
Create a PostgreSQL database, create a web service from the GitHub repository, set DATABASE_URL to the database's internal URL, set VIANOVA_SECRET_KEY, build with pip install -r requirements.txt and start with gunicorn app:app. Health check path: /health.
