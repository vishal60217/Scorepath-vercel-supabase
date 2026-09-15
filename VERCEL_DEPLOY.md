# Vercel deployment

Use the repository root as the Vercel Root Directory (`.`). This project deliberately has no `public/` folder and no API rewrite. Express serves the website and API from one application.

Required environment variables:
DATABASE_URL
ADMIN_EMAIL
ADMIN_PASSWORD
ADMIN_NAME

Optional payment variables:
RAZORPAY_KEY_ID
RAZORPAY_KEY_SECRET
RAZORPAY_WEBHOOK_SECRET
BANK_NAME
BANK_ACCOUNT_NAME
BANK_ACCOUNT_NUMBER
BANK_IFSC
UPI_ID
SUPPORT_EMAIL

After changing environment variables, redeploy.
