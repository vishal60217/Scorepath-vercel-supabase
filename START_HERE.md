# SCOREPATH — START HERE

This is the final production-oriented build.

### 1. GitHub
Upload the files in this project directly into the root of a GitHub repository.

You should see at the repository root:

- `server.js`
- `package.json`
- `vercel.json`
- `public/`
- `data/`

There should NOT be another `ScorePath` folder around these files.

### 2. Vercel
Import that GitHub repository. Keep the project Root Directory as `.` / repository root. Do not add a rewrite for `/api`.

### 3. Environment variables
Add `DATABASE_URL`, `DATABASE_SSL`, `ADMIN_EMAIL`, `ADMIN_PASSWORD`, and `ADMIN_NAME`.
Use Supabase's **Transaction pooler** connection string for `DATABASE_URL` because this app runs as a Vercel serverless/Fluid Compute Express application.

### 4. Test
Open `/api/health` on the deployed domain. It must return JSON, not the homepage.

### 5. Admin
Open the site, log in with `ADMIN_EMAIL` / `ADMIN_PASSWORD`, then configure bank/UPI details and live-class links from the admin area.

### 6. Payments
Razorpay works when its environment variables are configured. Without Razorpay, customers can use manual bank/UPI proof and an admin can approve the UTR.
