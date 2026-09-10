# CargeX — Production Deployment Package

Full-stack Express + SQLite CargeX delivery tracking website with a blue-and-white logistics design, customer tracking, and an admin portal.

## Production changes
- SQLite database path can be configured with `CARGEX_DATA_DIR`; Railway automatically uses `RAILWAY_VOLUME_MOUNT_PATH` when present.
- Secure HTTPS-only session cookies when `NODE_ENV=production`.
- Production startup refuses to run without a strong `SESSION_SECRET` (32+ characters).
- `/health` endpoint for deployment health checks.
- Admin password-change page at `/admin/account` with a 12-character minimum.
- Tracking numbers include a short uniqueness suffix to reduce collisions.

## Local run
1. Install Node.js 18+ (20+ recommended).
2. Run `npm install`.
3. Set `SESSION_SECRET` to a random 32+ character value (production requires it).
4. Run `npm start`.
5. Open `http://localhost:3000`.

## Production / Railway
1. Push the contents of this folder to a private GitHub repository.
2. Create a Railway project and deploy the GitHub repository as a Node service.
3. Set these Railway service variables:
   - `NODE_ENV=production`
   - `SESSION_SECRET=<strong random 32+ character secret>`
4. Attach a Railway Volume to the CargeX service and set its mount path to `/app/data`.
5. Set `CARGEX_DATA_DIR=/app/data` as a service variable. (Alternatively, the app will use Railway's `RAILWAY_VOLUME_MOUNT_PATH` automatically.)
6. Deploy and generate a public domain from Railway Networking.
7. Test `https://YOUR-DOMAIN/health`, `https://YOUR-DOMAIN/track`, and `https://YOUR-DOMAIN/admin/login`.

Railway Volumes persist application data across deployments and restarts. Mount the volume at `/app/data` because Railway places the application under `/app`.

## Admin
Initial account (change immediately):
- Email: `admin@cargex.com`
- Password: `ChangeMe123!`

After the first login, open `/admin/account` and set a strong password of at least 12 characters.

## Important
- Do not commit `.env` files, production secrets, or the SQLite database to GitHub.
- Use a private GitHub repository.
- Replace `support@cargex.com` with your real support address before launch.
- Only publish tracking records for genuine shipments and accurate status updates.
