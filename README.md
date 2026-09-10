# CargeX — Professional Delivery Tracking Website

Full-stack Express + SQLite delivery tracking website with a polished blue-and-white logistics design and working admin portal.

## Features
- CargeX branded responsive homepage
- Professional hero section and shipment tracker
- Unique tracking numbers such as `CARGEX-2026-000001`
- Customer tracking page with shipment timeline
- SQLite database for shipments and tracking events
- Admin login and dashboard
- Create shipments and automatically generate tracking numbers
- Publish status/location updates visible to customers
- Mobile responsive layout

## Run locally
1. Install Node.js 18+.
2. Open this folder in a terminal.
3. Run `npm install`.
4. Run `npm start`.
5. Open `http://localhost:3000`.

## Admin
Open `http://localhost:3000/admin/login`

Initial credentials:
- Email: `admin@cargex.com`
- Password: `ChangeMe123!`

**Before production:** change the default admin password, set a strong `SESSION_SECRET`, enable HTTPS, set secure cookies, and use a production database/host as appropriate.

## Notes
The website uses CargeX's own branding and design rather than copying DHL/FedEx trademarks or logos. Replace the placeholder contact email (`support@cargex.com`) with your real business address before launch.
