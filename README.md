<div align="center">
  <img src="assets/icon.png" alt="SFS Logo" width="120" height="auto" />
  <h1>Santosh Filling Station (SFS) Management System</h1>
  <p><strong>Next-Generation Cross-Platform SaaS for Fuel Station Automation</strong></p>
  <p>
    <img alt="Version" src="https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000" />
    <img alt="Capacitor" src="https://img.shields.io/badge/Capacitor-Android_iOS-blueviolet.svg" />
    <img alt="Firebase" src="https://img.shields.io/badge/Firebase-Firestore-orange.svg" />
  </p>
</div>

---

## ⚡ Overview
**SFS Dashboard App** is a highly specialized, glassmorphism-themed financial management system built identically for Petrol Pump Managers and shift workers. Instead of relying on archaic paper ledgers, it provides a seamless interface capable of automatically calculating complex nozzle differences (Ltrs), reconciling exact expected monetary cash differences natively against exact actual cash drops, managing real-time staff debts, and tracking real-time un-cleared lent transactions.

## 🚀 Key Features

* 📱 **Cross-Platform Compatibility:** Runs simultaneously as a lightning-fast Web App and natively as an **Android App** via Capacitor.
* 💸 **Automated Day-to-Day Reconciliations:** Advanced algorithm accurately aggregates H.S.D. and M.S. fuel nozzle differences automatically parsing un-cleared cash, online payments, and expenditures to flag immediate shortages.
* 🔍 **Unified Debt Engine:** Replaced manual entry forms with a powerful aggregated `Lent Database Search Engine`. Search any borrower’s name and instantly compile their debt histories across daily shift files!
* 📊 **One-Click Audit Reporting:** Automatically extracts fully-branded **PDF Overviews** (via `jsPDF`) decorated with SFS watermarks, alongside deep-dive **Excel Spreadsheets** automatically formatted for accountants. 
* 📡 **Firebase Cloud Sink:** Instantaneous cloud syncing allows a petrol pump employee to submit their shift via an Android device while the pump-owner views reports rendered instantly on their web-portal.
* 💾 **Offline Draft Protocol:** Built-in persistence engines allow staff to start complex machine readings and safely refresh their browsers without losing a single character of typed data.
* 🎨 **Liquid Glassmorphism UI:** Complete premium, minimalist translucent frontend layout using raw Tailwind CSS.

## 🛠️ Technology Stack
- **Frontend Core:** Vanilla HTML5, ES6 JavaScript, `TailwindCSS` (CDN).
- **Backend & Database:** `Firebase App` + `Firebase Firestore` (Cloud Synchronization).
- **Mobile Containerization:** `CapacitorJS` (Android Native Execution).
- **Exporting Libraries:** `jsPDF`, `jsPDF-AutoTable`, `SheetJS` (XLSX).
- **Iconography:** `FontAwesome`.

## 📦 Setting Up the Environment

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/sfs-dashboard.git
   cd sfs-dashboard
   ```

2. **Install Capacitor Dependencies:**
   ```bash
   npm install
   ```

3. **Running the Web App Locally:**
   Simply launch the `public/index.html` file in any modern browser or using a fast local server:
   ```bash
   npx serve public
   ```

4. **Syncing to Android Studio:**
   Any time you modify the core code inside `/public`, synchronize the data directly to the native Android build via:
   ```bash
   npx cap sync android
   ```
   *To launch the project inside the IDE:*
   ```bash
   npx cap open android
   ```

## 🔒 Firebase Security Overview
Authentication is internally strictly controlled by the UI login gateway mapping to `sfs_users` on Firestore. App states are saved via isolated `setDoc` and `getDoc` calls bound directly inside `sfs_production/app_state`.

## 👨‍💻 Developer Notes
This system is strictly isolated via `DOMContentLoaded` triggers initializing dynamic arrays logic locally before comparing signatures to the Firebase Cloud. Modifying the DOM state objects directly (`state.shifts`, `state.lentRecords`) triggers the UI reflow rendering functions (e.g. `renderReports()`, `renderLentRecords()`).

*(Made dynamically by Suraj Debnath)*
