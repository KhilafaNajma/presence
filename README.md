# PresenceGate Selfie Edition

## Features
- Shared attendance across browsers using Netlify Functions and Blobs
- Live front-camera capture only; there is no file/gallery input
- Browser-side JPEG compression at 640 px and ~68% quality
- Selfie required for check-in and presence verification; optional for check-out
- Random liveness prompt, rotating presence code, GPS geofence
- Server-side admin PIN, private admin selfie viewer, delete-selfie control
- Shared dashboard, muster list, manual checkout, CSV export

## Deploy
1. Push the COMPLETE extracted folder to GitHub.
2. Import the repository into Netlify. `netlify.toml` sets `public` and `netlify/functions`.
3. Add Netlify environment variables with Functions scope:
   - `ADMIN_PIN` = your fixed private PIN
   - `SESSION_SECRET` = a random value at least 32 characters long
4. Trigger a new production deploy.
5. Open Admin, configure the event and enable Attendance open.

## Privacy
The app collects participant ID, name, location/accuracy, timestamp, and camera image. Publish a retention policy and delete images when they are no longer required.

## Security limitation
The UI has no gallery upload. Nevertheless, browsers and modified devices may expose virtual cameras, so no browser-only selfie system can guarantee that every image came from an unmodified physical camera.
