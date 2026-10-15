# insightsmafia Billing (React + Node + Google Sheets)

## Google Sheet setup (one time)
1. Google Cloud -> create a project -> enable the **Google Sheets API**.
2. Create a Service Account -> Keys -> download the **JSON key**.
3. Create a new Google Sheet and copy the ID from its URL (`/d/<SHEET_ID>/edit`).
4. Share the sheet with the service account's `client_email` as **Editor**.
   The server creates the tabs (Parties, Items, Docs, Payments, Expenses, Settings) automatically.

## Run
cd server && cp .env.example .env   # fill SHEET_ID, GOOGLE_CREDENTIALS (one line), APP_PASSWORD
npm install && npm run dev          # http://localhost:5000
cd client && npm install && npm run dev   # http://localhost:5173

First open **Settings** and fill in business name, GSTIN and **State**, then add Parties and Items.

## Deploy
Client: Vercel/Netlify (set `VITE_API=https://<api-url>/api`). Server: Render/Railway, single instance (for the numbering lock).
