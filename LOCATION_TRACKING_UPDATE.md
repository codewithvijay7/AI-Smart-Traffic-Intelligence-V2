# Location selection and GPS tracking update

This update adds the first stage of location features to the existing project.

## Added
- Choose a source by clicking **Pick source on map** and then clicking the map.
- Choose a destination by clicking **Pick destination** and then clicking the map.
- Use the browser's GPS permission to set **My current location** as the source.
- Start/stop browser GPS watch and display the current device location marker on the map.
- Send selected map/GPS coordinates to the existing Flask route endpoint.
- Flask validates latitude/longitude and uses those coordinates for the existing weather and route calculation flow.

## Important scope note
The GPS marker currently updates on the device/browser where tracking is enabled. This is not yet shared multi-user tracking. Shared tracking requires user identity/authentication, a persistent location store, and a realtime transport (for example, authenticated WebSockets). Those should be added as the next stage rather than exposing anonymous location data.

## Run locally

Backend (from `backend`):
```bash
pip install -r requirements.txt
python app.py
```

Frontend (from `frontend`):
```bash
npm install
npm run dev
```

Browser GPS requires user permission and a secure context (HTTPS on deployed sites; localhost is permitted for local development). Keep API keys in local `.env` files and do not commit or share them.
