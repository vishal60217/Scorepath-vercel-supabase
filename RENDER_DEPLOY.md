# ScorePath — Render + Neon

This package is for a normal Node.js/Express Web Service on Render.

## Render settings
- Environment: Node
- Build Command: `npm install`
- Start Command: `npm start`
- Root Directory: leave blank

## Environment variables
- `DATABASE_URL` = your full Neon PostgreSQL connection string
- `DATABASE_SSL` = `true`
- `ADMIN_EMAIL` = your admin email
- `ADMIN_PASSWORD` = your strong admin password

Optional Razorpay: `RAZORPAY_KEY_ID`, `RAZORPAY_KEY_SECRET`, `RAZORPAY_WEBHOOK_SECRET`
Optional bank settings: `BANK_NAME`, `BANK_ACCOUNT_NAME`, `BANK_ACCOUNT_NUMBER`, `BANK_IFSC`, `UPI_ID`, `SUPPORT_EMAIL`

After deployment, test `/api/health`. Never share passwords or secrets.
