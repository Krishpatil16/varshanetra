# VARSHANETRA

AI-Powered Integrated Heavy Rainfall Early Warning and Inundation Prediction System.

## Status
This repository contains a working prototype focused on a modular, extensible architecture for a hydrological early-warning platform.

## Demo mode and data usage
The initial implementation is intentionally configured in DEMO mode. It uses historical/synthetic sample data generated for a pilot region and clearly labels all alerts and forecasts as DEMO / HISTORICAL DATA. It is designed to be replaced by real sources via the adapter architecture without altering the rest of the pipeline.

## Quick start

- Backend: `cd backend && python -m uvicorn app.main:app --reload`
- Web client: `cd frontend && npm install && npm run dev`
- Android client: `cd apps/android && npm install && npx expo start`

## Public deployment

The repository includes `render.yaml` for deploying the demo API and web client on Render. Create a new Blueprint from the GitHub repository in Render; it will provision both services and expose the web service URL for the team. The demo data remains clearly labeled as historical/synthetic data.

The web and Android clients consume the same FastAPI endpoints. Android uses `http://10.0.2.2:8000` for the Android emulator; set `EXPO_PUBLIC_API_BASE_URL` for a physical device.

## Client experience

The web client is a responsive emergency operations console with a mobile bottom navigation, location search/current-location action, risk map, layer toggles, replay timeline, forecast analytics, alerts, infrastructure exposure, explainability, data-source health, and model monitoring.

The Android client is an Expo mobile experience with Home, Map, Alerts, Insights, and Profile tabs. It includes a mobile risk card, location permission flow, risk stories, draggable-style map bottom-sheet layout, alert acknowledgement action, and shared backend data loading.

## Modules
- Data ingestion
- Data quality and normalization
- Fusion and feature engineering
- rainfall forecasting baseline
- inundation risk scoring
- alert generation
- GIS dashboard backend API
- reproducible model configuration

See the docs directory for detailed architecture notes.
