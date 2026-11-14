# Placement Preparation Portal

A Flask-based student placement preparation portal with aptitude tests, coding practice, interview preparation, company information, and student progress tracking.

## Run locally

```bash
cd "Placement Preparation Portal/Placement Preparation Portal"
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
python app.py
```

Open http://127.0.0.1:5000.

## Deploy on Render

This repository includes a `render.yaml` Blueprint. It configures a Python web service in Singapore, installs dependencies, runs the app with Gunicorn, and mounts a persistent disk at `/var/data` for SQLite storage. The disk-backed service uses Render's paid Starter instance; review the plan and disk cost in Render before applying.

1. Open https://dashboard.render.com/blueprint/new?repo=https://github.com/Jaswanth77777/placement-preparation-portal
2. Connect GitHub if prompted.
3. Review the service, Starter plan, Singapore region, and persistent disk.
4. Apply the Blueprint. Render generates `SECRET_KEY` automatically.

The health endpoint is `/health`. SQLite data is stored at `/var/data/placement_portal.db` in production.

## Notes

- Do not commit `.env` files or secrets.
- The checked-in SQLite files are legacy repository artifacts; the deployed app uses the persistent-disk database path configured by Render.
