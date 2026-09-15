# ScorePath — final Vercel deployment

## Important
Deploy the **repository root** exactly as this ZIP is structured. Do not put the project inside another folder.

The final architecture uses Vercel's native Express deployment model:

- `server.js` = Express application entrypoint
- `public/` = website files
- `vercel.json` = headers only; no API rewrite
- `/api/*` = handled directly by Express

This avoids the previous `/api/health` → homepage routing problem.

## Vercel environment variables

Add these in Project → Settings → Environment Variables:

Required for production database:
- `DATABASE_URL` = the **Supabase Transaction Pooler** connection string from Supabase → Connect → Transaction pooler
- `DATABASE_SSL` = `true`
- `ADMIN_EMAIL` = your admin email
- `ADMIN_PASSWORD` = a strong admin password
- `ADMIN_NAME` = ScorePath Admin

Optional payments:
- `RAZORPAY_KEY_ID`
- `RAZORPAY_KEY_SECRET`
- `RAZORPAY_WEBHOOK_SECRET`

The application can also use bank/UPI manual payment. Configure those from Admin → Bank & settings after login.

## First test after deployment

Open:

`https://YOUR-VERCEL-DOMAIN/api/health`

A healthy production response contains:

- `service: "ScorePath"`
- `productionReady: true`
- `database: "postgres"`
- non-zero course/lesson/plan counts

If `/api/health` displays the ScorePath homepage instead, the wrong repository/root directory was deployed. Do not change the database settings; fix the Vercel deployment source/root first.
