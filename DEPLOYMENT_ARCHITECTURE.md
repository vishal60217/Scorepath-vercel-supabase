# ScorePath 7.0 deployment architecture

This build intentionally uses Vercel's native Express deployment model.

- `server.js` is the Express application entrypoint.
- `public/` contains all browser assets.
- There is no `/api` rewrite and no catch-all rewrite in `vercel.json`.
- `/api/*` is handled by Express itself.
- `/api/health` is therefore a real backend endpoint, not the homepage.
- Supabase Transaction Pooler is used for serverless PostgreSQL connections.

Vercel's current Express documentation says Express apps can be deployed with the application entrypoint and that static assets should live under `public/`. Supabase recommends transaction pooling for serverless functions.
