# Flutter Frontend

Ports and environment
- Backend base URL should point to http://localhost:3001
- Web preview port target: 3000

Setup
1) Copy .env.example to .env
   - BACKEND_BASE_URL=http://localhost:3001
2) Install dependencies
   - flutter pub get
3) Run
   - For web: flutter run -d chrome --web-port 3000

Notes
- The dashboard performs a connectivity check to GET /api/health on initialization and displays the backend status.
