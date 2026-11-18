# FitGuru AI — Fitness & Nutrition Coach

A React + TypeScript fitness dashboard with workout planning, guided workout sessions, nutrition tracking, hydration tracking, progress history, browser voice features, and an optional Google Gemini-powered coach. The app also includes local fallback coaching and workout/meal generation when no API key is configured.

## Requirements

- Node.js 20.19+ (or 22.12+)
- npm

## Install and run

From the project folder, run:

```bash
npm ci
npm run dev
```

Open the local URL printed by Vite (normally `http://localhost:5173`).

On Windows PowerShell, use `npm.cmd ci` and `npm.cmd run dev` if PowerShell blocks the npm script.

## Production build

```bash
npm run build
npm run preview
```

The production files are generated in `dist/`.

## Optional Gemini integration

The app works without an API key using its built-in local engine. To enable Gemini:

1. Copy `.env.example` to `.env.local`.
2. Set `VITE_GEMINI_API_KEY` to your Google AI Studio API key, or enter the key in the app's Settings screen.
3. Restart the development server after changing `.env.local`.

**Security note:** Variables prefixed with `VITE_` and API keys entered into a browser app are exposed to the client. This setup is suitable for local testing, not for protecting a production secret. For a public deployment, move Gemini requests behind a server-side API and keep the key on the server.

## Project structure

- `src/App.tsx` — application shell and tab routing
- `src/components/` — coach, workout, nutrition, progress, vision, and settings UI
- `src/data/` — preset workouts, meals, coaches, and exercise library
- `src/services/` — Gemini integration, browser audio, and local storage
- `src/types/` — shared TypeScript models

## Notes

- User profile, settings, workout routines, meal plans, and workout history are stored in the browser's local storage.
- Camera and microphone features require browser permission and generally work on `localhost` or HTTPS.
- Fitness and nutrition guidance is informational and is not a substitute for advice from a qualified healthcare professional.
