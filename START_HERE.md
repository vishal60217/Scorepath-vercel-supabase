# ScorePath Ultimate — Start Here

This package is the complete ScorePath website project.

## What is included

- Premium modern/vintage IELTS/PTE landing page
- Responsive mobile layout
- Course catalogue and lesson viewer
- IELTS/PTE diagnostic practice test
- Student registration/login/logout
- Student dashboard and lesson progress
- Membership plans
- Razorpay integration when keys are configured
- Bank/UPI payment proof + UTR workflow
- Admin dashboard
- Course/lesson/plan/teacher/live-class CRUD
- Payment approval/rejection
- Bank/UPI settings
- Supabase PostgreSQL persistence
- Vercel serverless API
- Health endpoint
- Graceful content fallback if the database is temporarily unavailable

## Vercel setup

1. Upload the **contents of this folder** to GitHub. `index.html`, `package.json`, `vercel.json`, `api/`, `server.js`, `app.js`, and `styles.css` must be at the repository root.
2. Import that GitHub repository into Vercel.
3. In Vercel → Settings → Environment Variables add:
   - `DATABASE_URL`
   - `DATABASE_SSL` = `true`
   - `ADMIN_NAME`
   - `ADMIN_EMAIL`
   - `ADMIN_PASSWORD`
4. For `DATABASE_URL`, copy the Supabase **Shared/Session Pooler** connection string. This build automatically switches a Supabase pooler URI from port 5432 to the serverless-friendly transaction pooler port 6543.
5. Redeploy after saving the variables.

## First check

Open:

`https://YOUR-DOMAIN/api/health`

A working production setup should return JSON containing:

- `ok: true`
- `database: "postgres"`
- `productionReady: true`

Then open the normal homepage.

## Admin

Use the exact `ADMIN_EMAIL` and `ADMIN_PASSWORD` you configured in Vercel. The first successful database initialization creates the admin account automatically.

## Important

Do not put database passwords, admin passwords, Razorpay secrets, or other private keys into GitHub or the website code.
