# DIDOU PHONE — Algerian Smartphone Store

A responsive smartphone shop with product search/filtering, shopping bag, cash-on-delivery order submission, and a protected admin dashboard.

## Requirements
- Node.js 20 or newer
- npm

## Run locally
1. Extract this ZIP and open a terminal in the project folder.
2. Install dependencies:
   `npm install`
3. Copy `.env.example` to `.env`.
4. Set a strong `SESSION_SECRET` and `ADMIN_PASSWORD` (at least 12 characters). Keep `.env` private; never upload it to public GitHub.
5. Start:
   `npm start`
6. Open `http://localhost:3000` for the shop.
7. Open `http://localhost:3000/admin.html` for admin login.

The admin account is created on first startup only when `ADMIN_USERNAME` and `ADMIN_PASSWORD` are set and the password is at least 12 characters. There is no hard-coded default admin password.

## Features
- Responsive store homepage and product cards
- Search and brand filters
- Cart saved in the customer's browser
- Cash-on-delivery order form
- Server-side price and stock validation; stock is deducted on order
- Admin login with hashed password, session cookie, and login rate limiting
- Admin dashboard with product CRUD, order list/status updates, inventory and summary stats
- SQLite database persists products, orders, admin account and sessions

## Before public launch
- Deploy on a host with persistent disk storage for SQLite, or migrate to PostgreSQL.
- Set `NODE_ENV=production`, a long random `SESSION_SECRET`, and HTTPS.
- Set store phone and delivery details in environment variables.
- Replace demo products/prices with actual stock and photos.
- Configure real delivery fees and confirm orders with customers.
- Add a privacy notice and terms, and arrange backups.
- This starter does not process online card payments; orders are cash-on-delivery.

## Deploy to Render
1. Push the project files (including `render.yaml`) to a GitHub repository.
2. In Render, choose **New + → Blueprint**, connect that repository, and deploy.
3. When prompted, enter a strong `ADMIN_PASSWORD` (at least 12 characters). `SESSION_SECRET` is generated automatically.
4. After deployment, open `/admin.html` and sign in with username `admin` and the password you entered.

Important: the free Render filesystem is ephemeral. This starter uses SQLite, so products/orders may reset after redeploy or instance replacement. Use persistent storage or a managed PostgreSQL database before accepting real customer orders.
