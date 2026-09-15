# ScorePath — FINAL Vercel deployment

This version intentionally keeps `index.html`, `app.js`, and `styles.css` at the repository root. Do not place the project inside another folder.

Repository root must directly contain:
- package.json
- server.js
- index.html
- app.js
- styles.css
- favicon.svg
- robots.txt
- sitemap.xml

Vercel:
- Root Directory: `.`
- Framework Preset: Express (or Other if Express is not offered)
- Build Command: leave empty
- Output Directory: leave empty
- Install Command: `npm install`

After deployment:
- `/` = ScorePath website
- `/api/health` = JSON health check
- `/api/content` = content API
- `/app.js` = frontend JavaScript
- `/styles.css` = stylesheet

Do not upload the ZIP file into GitHub. Extract it and upload the files inside it.
