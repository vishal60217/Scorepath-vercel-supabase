# ScorePath — Vercel + Supabase

This build is prepared for Vercel with Supabase PostgreSQL.

## Required Vercel Environment Variables

Set these in **Vercel → Project → Settings → Environment Variables**:

- `DATABASE_URL` — the Supabase **Shared/Session Pooler** PostgreSQL URI copied from Supabase Connect.
- `DATABASE_SSL` — `true`
- `ADMIN_NAME` — your admin display name
- `ADMIN_EMAIL` — the email you will use for Admin login
- `ADMIN_PASSWORD` — a strong admin password

Optional:

- `RAZORPAY_KEY_ID`
- `RAZORPAY_KEY_SECRET`
- `RAZORPAY_WEBHOOK_SECRET`
- `BANK_NAME`
- `BANK_ACCOUNT_NAME`
- `BANK_ACCOUNT_NUMBER`
- `BANK_IFSC`
- `UPI_ID`
- `SUPPORT_EMAIL`

### Important

Never commit `DATABASE_URL`, passwords, or Razorpay secrets to GitHub. Vercel Environment Variables are the correct place for secrets.

The application automatically creates its PostgreSQL tables and seeds the built-in ScorePath courses, lessons, membership plans, teachers, live classes, questions, and settings on first successful database initialization.

## Deployment

1. Upload this project to a new GitHub repository.
2. Import the repository into Vercel.
3. Add the required environment variables above.
4. Deploy.
5. Open `/api/health` on the deployed domain. It should report `ok: true`, `database: "postgres"`, and `productionReady: true`.
6. Open `/api/courses` to verify seeded course content.
7. Log in using `ADMIN_EMAIL` and `ADMIN_PASSWORD` to access the Admin panel.
