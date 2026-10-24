# Kirana Connect (POC)

> **Pickup-First Hyperlocal Grocery Ordering Platform for Tier-2 & Tier-3 Indian Cities**

Kirana Connect connects customers with trusted neighborhood grocery (*kirana*) stores. Customers browse daily essentials, place pickup orders online, select convenient time slots, and collect packed groceries directly from the store counter with zero delivery charges and payment at pickup (Cash / UPI).

---

## 🛠️ Tech Stack & Architecture

- **Architecture:** Single Codebase Modular Monolith deployable on **Vercel**
- **Framework:** Next.js 14+ (App Router, Server Components & Route Handlers)
- **Language & Styling:** TypeScript + Tailwind CSS (Mobile-First Responsive Design)
- **Database:** MongoDB Atlas (Official `mongodb` Node.js driver with built-in instant dev fallback)
- **Authentication:** Firebase Phone Authentication (Client) + Firebase Admin SDK (Backend token verification) + 1-Click Persona Simulator for POC evaluation
- **Real-Time Order Updates:** Automatic background polling (every 4 seconds)

---

## 🚀 Getting Started

### 1. Environment Setup
Copy `.env.example` to `.env.local`:
```bash
cp .env.example .env.local
```

Configure your MongoDB Atlas URI and Firebase credentials if available (or run immediately out-of-the-box using the pre-configured in-memory POC state).

### 2. Install Dependencies
```bash
npm install
```

### 3. Run Development Server
```bash
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 👥 Core User Roles & Evaluation Guide

Use the top **POC Role Switcher** or the **Login Page** to switch between personas in 1 click:

1. **Customer Persona (Aman Sharma):**
   - Browse partner stores in Indore, Varanasi, or Jaipur.
   - Filter items by category (Atta & Flour, Oils, Dal, Masalas, etc.).
   - Add items to cart (enforces single-store rule with clear conflict prompt).
   - Choose a pickup slot (e.g. *Today, 05:00 PM - 06:00 PM*).
   - Place order (*Pay at store via Cash/UPI*).
   - Watch live status progression via 4-second polling ticker.

2. **Merchant Persona (Ram Prasad Gupta - Gupta Kirana):**
   - Go to `/merchant` dashboard.
   - View new incoming orders.
   - Accept or decline order with 1 click.
   - Progress order to *Packing Items* &rarr; *Mark Ready for Pickup* &rarr; *Mark Picked Up & Paid*.
   - Go to `/merchant/inventory` to toggle in-stock/out-of-stock and update daily grocery selling prices.

3. **Admin Persona (Platform Ops):**
   - Go to `/admin` dashboard.
   - View marketplace metrics: Total Orders, Active Stores, GMV, Commission earnings.
   - Click **"Seed Sample Kiranas & Products"** to populate the catalog.
   - Go to `/admin/merchants` to verify new store partners and adjust commission rates.

---

## 📂 Key Architecture Mapping
For full UI component, API route, and MongoDB collection details, see [`docs/ui-business-mapping.md`](docs/ui-business-mapping.md).
