# MCS4302 Week 4 – Resilient Mobile Client-Server Communication

Index number: 24441155

- `backend/` – FastAPI backend with fault-injection endpoints (`/items`, `/slow`, `/flaky`, `/bad-json`, `/reset`)
- `lib/` – Flutter client (Parts 2–5): JSON model, `ApiClient` with timeouts and error classification,
  exponential backoff with ±20% jitter, idempotency keys, and the retry measurement experiment
- `android/app/src/main/AndroidManifest.xml` – INTERNET permission and cleartext HTTP for the local lab
- `Measurement_24441155.pdf` – measurement sheet

## Run
Backend:
```
cd backend
python -m venv .venv
.venv\Scripts\activate          # macOS/Linux: source .venv/bin/activate
python -m pip install -r requirements.txt
python -m uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```
App (the emulator reaches the host at http://10.0.2.2:8000):
```
flutter pub get
flutter run
```
