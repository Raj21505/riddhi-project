# Run Integrated App (Backend + Frontend)

Start the app with uvicorn from project root:

```bash
uvicorn backend.main:app --reload
```

Then open:

- `http://127.0.0.1:8000`

The backend serves the frontend automatically, and `/` opens the first frontend page (`index.html`).

API health check:

- `http://127.0.0.1:8000/api/health`

## API URL behavior in frontend

Frontend scripts resolve API URL as:

- `localStorage.SDSS_API_URL` if set
- `http://localhost:8001` when opened from `file://`
- `window.location.origin` otherwise (including `localhost` / `127.0.0.1`)