# flutter_frontend

Mobile app interface for site verification and workflow management.

## Ocean Professional Theme
- Primary: `#2563EB`
- Secondary/Success: `#F59E0B`
- Error: `#EF4444`
- Background: `#f9fafb`
- Surface: `#ffffff`
- Text: `#111827`

## Setup
1) Install dependencies:
   - Flutter (stable)
   - Android/iOS tooling as needed

2) Install packages:
   ```
   flutter pub get
   ```

3) Configure environment:
   - Copy `.env.example` to `.env`
   - Adjust variables as needed
   - Defaults:
     - `BACKEND_BASE_URL=http://localhost:3001`
     - `API_TIMEOUT_MS=15000`

4) Run:
   ```
   flutter run
   ```
   - On web: `flutter run -d chrome`
   - Note: Preview runs at port 3000 typically for web devtools; backend default in this project is on `3001`.

## Features
- Dotenv-based API configuration
- Minimal auth (JWT login)
- Dashboard with site list and status chips
- Site detail with verifications and "Run Verification"
- Workflow screen listing steps with completion action
- Provider/ChangeNotifier state management
- Graceful error messaging, basic retry on network calls

## Environment Variables
See `.env.example`.

## Project Structure
- `lib/theme.dart` — Theme and UI helpers
- `lib/api/api_client.dart` — API client and endpoints
- `lib/models/models.dart` — Data models
- `lib/state/app_state.dart` — Global state
- `lib/screens/*.dart` — Screens (Dashboard, Site Detail, Workflow)
- `lib/main.dart` — Entry point with bottom navigation and login

## Notes
- Login endpoint expected at `/api/auth/login/` returning a JWT token as `access` or `token`.
- Health check at `/api/health`.
- Sites endpoints:
  - `GET /api/sites/`
  - `GET /api/sites/{id}/`
  - `GET /api/sites/{id}/verifications/`
  - `POST /api/sites/{id}/verify/`
  - `GET /api/sites/{id}/workflow-steps/`
- Workflow:
  - `POST /api/workflow-steps/{id}/complete/`

Adjust paths as needed if backend differs.
