# QASHVERO — GitHub + Vercel starter

QASHVERO is a React/Vite business-finance dashboard starter. It includes a responsive workspace and locally working demo flows for transactions, sales, expenses, products, customers, invoices, suppliers, goals, approvals, audit history, charts, and currency display.

## Run locally

1. Install Node.js (LTS).
2. Extract this project.
3. Open a terminal in this folder and run:

   ```bash
   npm install
   npm run dev
   ```

4. Open the local address printed by Vite.

Create a production build with `npm run build`.

## Upload to GitHub

1. Create a new empty repository on GitHub named `qashvero`.
2. Extract this ZIP on your computer.
3. Upload the **contents** of this folder to the repository root (not the ZIP file itself), or use Git:

   ```bash
   git init
   git add .
   git commit -m "Initial QASHVERO application"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/qashvero.git
   git push -u origin main
   ```

4. On Vercel, choose **Add New → Project**, import the GitHub repository, and deploy.
5. Vercel should detect Vite. Build command: `npm run build`; output directory: `dist`.

## What works in this starter

- Responsive dashboard and navigation for the requested QASHVERO modules.
- Add and view demo transactions, sales, expenses, products, customers, invoices, suppliers, and goals.
- Local browser persistence using `localStorage`.
- Revenue/expense charts (the dashboard chart is clearly illustrative sample data).
- Currency display selector using browser currency formatting for the included common currency codes.
- Basic local approval actions, low-stock / pending / large-amount review flags, scenario calculator, audit log, and JSON data export.
- Subscription screen showing the requested 3-month trial and ₦3,500/month plan.

## Important: before accepting real customers or payments

This is a **frontend MVP/demo**, not a production accounting or payment platform. Records are saved only in the current browser. There is no secure login, shared database, multi-tenant isolation, live FX-rate service, production accounting engine, AI backend, background automation, or payment gateway connected yet. Sample chart history and sample records are illustrative.

For production, add:
- Supabase (or another backend) for authentication, PostgreSQL storage, row-level security, tenant isolation, backups, and server-side validation.
- Paystack or Flutterwave hosted/tokenised checkout for Visa/Mastercard and recurring billing. Do not build a form that stores raw card numbers or CVV. Use server-side secret keys and verified webhooks.
- A clear opt-in for the recurring charge after the 3-month free trial, trial-end reminders, cancellation, receipts, refunds, and billing history.
- A trusted FX-rate API with rate source and timestamp. The currency selector in this starter changes display formatting only; it does **not** convert amounts or fetch exchange rates.
- A server-side AI integration. Keep OpenAI API keys on the server, never in frontend code.
- Proper accounting rules, audit immutability, permissions, approval limits, reconciliation logic, and independent testing before using it for financial records.

## Environment variables

`.env.example` lists placeholders. Do not commit real secrets. Frontend variables prefixed with `VITE_` are visible to browsers, so only put public client keys there. Keep payment secret keys and AI keys in Vercel server-side environment variables / backend functions.

## Currency note

The currency dropdown includes common currencies and formats amounts with `Intl.NumberFormat`. It does not currently perform foreign-exchange conversion. Never treat the displayed figures as converted balances until an FX provider and base-currency ledger are implemented.
