# Photons — Attendance Prototype

A lightweight React + Vite prototype for classroom attendance using face detection and QR codes.

Key features
- Face scan page using face-api.js for on-device detection
- QR code generator and scanner for teachers and students
- Simple attendance logging UI and mock biometric component

Tech stack
- Frontend: React 19 + Vite
- Face detection: `face-api.js` (models in `public/models`)
- QR: `html5-qrcode`, `qrcode.react`, `react-qrcode-logo`
- Bundler: `vite`

Project structure
- `index.html` — app entry
- `src/` — React source
	- `App.jsx`, `main.jsx` — app bootstrap
	- `components/` — reusable UI pieces
	- `pages/` — route pages (FaceScan, QRGenerator, StudentPortal, TeacherDashboard, etc.)
- `public/models/` — face-api.js model files (already included)
- `package.json` — scripts and dependencies

Prerequisites
- Node.js 18+ and npm

Quick start (development)
1. Install dependencies:

```bash
cd attendance-prototype
npm install
```

2. Start dev server (Vite with hot reload):

```bash
npm run dev
```

3. Open the app in your browser at the URL shown by Vite (e.g., http://localhost:5173/Photons-Prototype/).

Build and preview (production)

```bash
npm run build
npm run preview
```

Deploy
- This project includes a `deploy` script which builds and publishes to GitHub Pages using `gh-pages`:

```bash
npm run deploy
```

Notes & usage tips
- Face models: `public/models` contains weights for the tiny face detector. Do not move these files; the face-scan page expects them at `/models/`.
- Camera access: pages that use camera will request permission. Use a secure origin (localhost or HTTPS) for camera APIs.
- If the face detector feels slow, try closing other apps or testing in Chrome/Edge with hardware acceleration.

Troubleshooting
- If the dev server URL shows a path like `/Photons-Prototype/`, open that exact path in the browser. If you want root `/`, edit `vite.config.js` `base` option.
- Model load errors: ensure `public/models` files are present. If running from a different base path, update load paths accordingly in `src/pages/FaceScan.jsx`.
- Port conflicts: Vite defaults to 5173; use `--port` if needed: `vite --port 3000`.

Contributing
- This is a prototype. Feel free to open issues or PRs for fixes and enhancements.

License
- MIT-style (no license file included).

Contact
- Repository: https://github.com/AyushPatwa11/SIH25_prototype---attendance

Enjoy exploring the prototype! If you want, I can also add a short `CONTRIBUTING.md` or update the `vite` base path.
