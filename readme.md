# 💰 FinTrack v5.0c — Family Hub

> **A zero-dependency, single-file Progressive Web App (PWA) for complete family wealth tracking, chit funds, broker portfolios, insurance policies, digital document vaults, and real-time multi-device cloud synchronization.**

![Version](https://img.shields.io/badge/Version-v5.0c-indigo?style=for-the-badge)
![Architecture](https://img.shields.io/badge/Architecture-Single--File%20PWA-emerald?style=for-the-badge)
![Database](https://img.shields.io/badge/Sync-Firebase%20RTDB%20%2B%20Offline--First-amber?style=for-the-badge)
![UI](https://img.shields.io/badge/UI-Tailwind%20CSS%20%2B%20Chart.js-sky?style=for-the-badge)

---

## 📖 Overview

**FinTrack v5.0c Family Hub** is an all-in-one personal and household financial management suite designed specifically for Indian families. Built as a self-contained single-file HTML Progressive Web App, it runs seamlessly offline via `localStorage` and synchronizes automatically across family devices via **Firebase Realtime Database (RTDB)** REST APIs.

---

## ✨ Key Features

### 📊 1. Executive Dashboard & Smart Alerts
* **Expandable Upcoming Reminders:** Automatically tracks and surfaces chit fund installments due within the next **15 days** (with month-end rollover logic) and insurance policy renewals due within **45 days**.
* **High-Contrast KPI Summary Tiles:** Instant overview of **Net Worth**, **Stocks & Mutual Funds**, **Monthly Outflows**, **Kids Log Totals**, **Active Chits Paid**, and **Family Lending**—complete with Indian numbering format (`₹`) and amount-in-words (`Lakhs` / `Crores`).
* **Asset Allocation Chart:** Interactive Chart.js doughnut breakdown of consolidated family wealth.
* **Broker Overview Grid:** Quick valuation snapshot across **AngelOne**, **Zerodha**, **Anand Rathi**, and other platforms.

### 🪙 2. Chits, Daily Pigmy & Family Lending
* **Monthly Chit Funds Register:** Track total chit value, monthly installment, paid installment progress bar, lifted status, and monthly interest costs on lifted chits—with 1-tap `+ Pay Month` logging.
* **Daily Pigmy Deposit Register:** Tracks daily pigmy collections by agent/bank with `+1 Day` / `-1 Day` adjustment controls.
* **Family Lending Receivables:** Record personal/family loans with automatic **Simple**, **Monthly Compounding**, or **Annual Compounding** interest accrual calculations from the lending date.

### 📈 3. Stocks & SIPs Portfolio
* **Multi-Owner & Multi-Broker Filtering:** Separate tracking for **Self**, **Spouse**, and **Joint** accounts across major Indian brokers.
* **SIP & Gain Analytics:** Monitors monthly SIP commitments alongside invested vs. current valuations and percentage returns.

### 🏦 4. Fixed Deposits, Insurance & Cash Reserves
* **Fixed Deposits Register:** Tracks principal amounts, interest rates (`% p.a.`), deposit dates, and maturity details across family members.
* **Insurance Portfolio:** Supports Life/Endowment, Term, ULIP, Health Mediclaim, and Vehicle policies. Automatically computes **Accumulated Amount Paid** (`Annual Premium × Policy Years Elapsed` from commence date) alongside **Surrender Value** and auto-calculates next renewal dates.
* **Liquid Reserves:** Track savings bank accounts, physical cash in hand, emergency funds, and digital wallets.

### 🧾 5. Expenses, Kids Log & Staff Payroll
* **Categorized Expense Tracking:** Filter between **Monthly Utilities/Recharges**, **Kids Log**, and **General Utilities**.
* **Dedicated Child Filtering:** Interactive summary tiles and filters for each child (customizable via Family Profile).
* **Staff & Salary Roll:** Manage household staff (drivers, cooks, maids) with monthly salary totals and payout dates.

### 🔐 6. Encrypted-Style Digital Vault & IDs
* Store sensitive family records (**Aadhaar**, **PAN**, **Vehicle RCs**, **Passports**, **Driving Licenses**, **Birth Certificates**, **Property Deeds**).
* Includes **1-tap copy to clipboard**, search/category filtering, and **60-day expiry warnings**.

### ⚖️ 7. Consolidated Net Worth Statement
* Full balance sheet comparing categorized **Total Assets** against **Outstanding Liabilities / Loans** to compute real-time consolidated Net Worth.

### ☁️ 8. Cloud Sync, Snapshots & Data Portability
* **Firebase Realtime Database Sync:** Two-way REST sync with configurable **Family Vault ID** (so multiple family members share the exact same database node) and optional database auth token. Includes automatic background polling every 30 seconds.
* **Snapshot Center:** Automatic point-in-time snapshots on every save (retaining the last 15 states) plus manual snapshots with 1-click state restoration.
* **Import / Export Suite:**
  * Export/Import full **JSON Backups** (via file upload or raw text paste with smart-quote sanitization).
  * **CSV Importer with Interactive Field Mapping** (supports uploading `.csv` files or pasting raw CSV data with live 2-row preview).
  * Export formatted **CSV Financial Reports**.
  * **Download Standalone HTML** (embeds your current data directly into a portable `.html` file).
* **Dual Themes & Fullscreen Mode:** Switch between **Crisp Light** and **Luxury Gold** themes, plus a distraction-free fullscreen toggle.

---

## 🛠️ Tech Stack

| Layer | Technology |
| :--- | :--- |
| **Core Architecture** | Single-File HTML5 / Vanilla JavaScript (ES6+) |
| **Styling** | Tailwind CSS (CDN) + Custom CSS Variables for Themes |
| **Data Visualization** | Chart.js |
| **Icons & Typography** | FontAwesome 6.4 + Google Fonts (`Inter`) |
| **Local Persistence** | Browser `localStorage` (`wealthtrack_pwa_data_v3`) |
| **Cloud Synchronization** | Firebase Realtime Database REST API |
| **Offline / PWA Support** | Inline Data-URI Web App Manifest + Blob Service Worker |

---

## 🚀 Getting Started

### Option 1: Run Locally
1. Clone or download the repository:
   ```bash
   git clone https://github.com/your-username/fintrack-family-hub.git
   ```
2. Open `fintrack_v4_1_family_hub.html` (or rename to `index.html`) directly in any modern browser (Chrome, Edge, Safari, Brave).

### Option 2: Host on GitHub Pages / Vercel / Netlify (Recommended for PWA Install)
1. Rename the HTML file to `index.html` and push it to your GitHub repository.
2. Enable **GitHub Pages** under **Settings → Pages → Deploy from branch (`main`)**.
3. Open your live HTTPS URL on Android (Chrome) or iOS (Safari) and tap **Install App** / **Add to Home Screen** to install FinTrack as a native standalone mobile app.

---

## ☁️ Configuring Firebase Realtime Database

FinTrack connects to Firebase RTDB out of the box via REST endpoints:

1. Create or open a project in the [Firebase Console](https://console.firebase.google.com/) and enable **Realtime Database**.
2. In **FinTrack**, click the **RTDB Cloud Sync** badge in the top bar (or the cloud icon on mobile).
3. Enter your **Firebase RTDB Endpoint URL** (e.g., `https://your-project-default-rtdb.firebaseio.com/`).
4. Set a unique **Family Vault ID** (e.g., `family_hub_v4`). Share this ID with family members so all devices read/write to `/fintrack_hub/<Family_Vault_ID>.json`.
5. *(Optional)* If your database rules require authentication, paste your **Database Secret / Auth Token** into the token field and click **Save & Sync Now**.

---

## 📂 Data Schema Overview

All records are stored in a unified JSON structure:

```json
{
  "familyProfile": { "selfName": "", "spouseName": "", "kid1Name": "", "kid2Name": "" },
  "chits": [],
  "pigmies": [],
  "stocks": [],
  "fixedDeposits": [],
  "insurance": [],
  "cashAccounts": [],
  "expenses": [],
  "employees": [],
  "lending": [],
  "liabilities": [],
  "digitalDocs": [],
  "snapshots": []
}
```

---

## 👤 Author & Contact

* **Developer:** S. C. Arun Kumar
* **Version:** `v5.0c` (Build 2026.11)
* **Contact:** +91 8105104599

---

## 📄 License

This project is open for personal and family financial management use. Feel free to fork and customize it for your household needs.