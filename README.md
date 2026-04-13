<div align="center">
  <img src="assets/icon.png" alt="SFS Logo" width="120" height="auto" />
  <h1>Santosh Filling Station (SFS) Management Dashboard</h1>
  <p><strong>An Enterprise-Grade, Cross-Platform Automated Petrol Pump Tracking System</strong></p>
  <p>
    <img alt="Version" src="https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000" />
    <img alt="Platform Details" src="https://img.shields.io/badge/platform-Web%20%7C%20Android-lightgrey" />
    <img alt="Capacitor" src="https://img.shields.io/badge/Powered_by-Capacitor-blueviolet.svg" />
    <img alt="Firebase" src="https://img.shields.io/badge/Database-Firebase_Firestore-orange.svg" />
  </p>
</div>

---

## ⚡ Executive Summary

The **SFS Dashboard App** is a highly specialized financial management SaaS custom-built for petroleum dispensing operations. It entirely replaces the archaic, highly-inaccurate paper ledger systems historically used by petrol pump managers. 

By utilizing dynamic form logic and real-time reconciliation algorithms, the system automatically calculates physical nozzle liter disparities against financial inflows to immediately detect cash shortages, missing money, and uncleared employee debts.

Built using a **Liquid Glassmorphism** design architecture wrapped in **CapacitorJS**, this codebase acts identically as both an ultra-fast desktop web application for pump owners, and a natively-installed Android application for pump employees working the floor.



## 🚀 Core Architectural Modules

The application is structured into four highly complex logic modules designed to strictly control capital cash flow. 

### 1. Day-to-Day (Master) Tracking Engine
This module is the heart of the pump's operations. Instead of manually multiplying rates, the user inputs the **Opening** and **Closing** meter readings for up to 4 nozzles across multiple machines.
- Automatically calculates Total Dispersed liters.
- Synchronizes with dynamic daily Fuel Rates (Petrol/M.S & Diesel/H.S.D).
- Calculates precise theoretical gross financial totals and subtracts online QR payments (PhonePe, GPay).
- **Cash Reconciliation Matrix:** Denomination-specific calculators (count of ₹500, ₹200, ₹100 wrappers) automatically subtract against physical bank drop-offs to spit out exact missing rupees (`Shortage / Excess`).

### 2. Unified Lent & Debt Search Array
Fuel stations frequently deal with "Borrowers" (truckers, corporate contracts) who take fuel on credit. 
- The system automatically scrapes all individual Employee shift notes to find *anyone* who took fuel on credit during that shift.
- That data is injected into a monolithic array.
- An instantaneous Frontend Search Filter allows managers to type a name (e.g. `Ramesh Express`) and see exactly how many times Ramesh took fuel over the month, totaling the absolute debt.

### 3. Staff Salary & Attendance Abstraction
Integrated modules allow pump managers to log when an advance is paid out against an employee's salary. When that employee runs their shift, their personal profile updates with their current financial standings.

### 4. Advanced Auditing & Branded Exports
For chartered accountants, the app possesses an on-board engine capable of instantly rebuilding the DOM arrays into readable business files.
- **jsPDF Injection:** Draws highly stylized PDF sheets featuring a diagonal 45-degree `SFS RECORDS` watermark backdrop.
- **SheetJS:** Generates completely flat `.xlsx` Excel spreadsheets summarizing column totals.
- All generators dynamically respect the active UI filters ensuring you only export what you are currently viewing.

---

## 🛠️ Technology Stack & Libraries

This is entirely a **Client-Side Heavy** application relying on raw DOM manipulation rather than abstracted VDOMs (like React), drastically improving native Android compilation speeds.

### Frontend Layer
- **Vanilla ES6 JavaScript:** Handling complex multidimensional calculations perfectly without framework bloat.
- **HTML5 & CSS3:** Structural DOM foundation.
- **TailwindCSS (via CDN):** Absolute layout control featuring complex `backdrop-blur-xl` and `bg-opacity` utilities to create the overarching liquid glass aesthetic.
- **FontAwesome:** Scalable SVG iconography.

### Sync & Persistence Layer
- **Firebase App (v10.8):** Cloud synchronization portal.
- **Firebase Firestore:** The entire application state is stored as a single, massive flattened JSON object at `sfs_production/app_state`. When the pump opens, it fetches the state and builds the DOM. On every modification, it rewrites the state natively.

### Native Build Containerization
- **CapacitorJS:** Wraps the entire web application inside an embedded Chromium WebView to deploy a pristine Android `.apk` / `.aab` bypassing traditional Java/Kotlin development.

---

## 💾 The Offline Protocol ("Drafts Mode")
Because petrol pumps often suffer from unreliable 4G connections, we built a redundant `localStorage` persistence protocol. 
1. As an employee types NOZZLE data into the interface, the app fires a localized cache-save routine.
2. Even if the browser forcibly closes or connection is lost, restarting the app retrieves the `drafts` object and automatically populates the DOM to the exact state it was left.

---

## 📦 Local Development & Setup Architecture

To compile, test, and render this application locally for debugging, follow the exact CLI sequence below.

### 1. Repository Setup
```bash
# Clone the private directory
git clone https://github.com/your-username/sfs-dashboard.git
cd sfs-dashboard

# Install absolute required Node modules (Capacitor Environment)
npm install
```

### 2. Live Web Development
The web application does not use Webpack or Vite. It is raw, static code. You simply need to launch it.
```bash
# Use any node server (e.g. npx serve)
npx serve public
```
*Navigate to `http://localhost:3000` to interact with the web interface.*

### 3. Android Compilation Pipeline
Whenever you change `public/index.html` or `style.css`, you **must** synchronize the fresh web assets into the Android native folder.
```bash
# Copies /public into the /android root
npx cap sync android

# Launches Android Studio with the newly bundled Web-App
npx cap open android
```
*(From inside Android Studio, simply click the ▶ Play button to push to an emulator or physical USB device).*

---

## 🔒 Security Configuration
Currently, routing bypasses complex middleware. A master `localStorage` token (`isLoggedIn=true`) guards the `DOMContentLoaded` router.
If users are required to authenticate, they pass through a static gate. Total system security relies exclusively on Firebase Firestore Database Rules validating incoming requests against valid registered endpoints.

---

## 📸 Application Gallery

<!-- Main Dashboard -->
<div align="center">
 <img width="1254" height="630" alt="image" src="https://github.com/user-attachments/assets/fab9c81b-cb82-47fc-845c-392b77681dff" />
  <p><em>Fig 1. The Main Management Dashboard featuring Liquid Glassmorphism UI and Real-Time Analytics.</em></p>
</div>

<!-- Day To Day -->
<div align="center">
  <img width="1919" height="897" alt="Day_To_Day" src="https://github.com/user-attachments/assets/f591f48b-0b8a-4923-a76e-e34b8ab0dc14" />
 <p><em>Fig 2. Interactive Nozzle Calculation Matrix automating H.S.D & M.S totals.</em></p>
</div>

<!-- Daily Shift -->
<div align="center">
<img width="1919" height="969" alt="Daily_Shift" src="https://github.com/user-attachments/assets/20637883-b54f-4bdf-bc99-6e95a74b3698" />
  <p><em>Fig 3. Comprehensive individual employee shift tracking interface.</em></p>
</div>

<!-- View Shift Record -->
<div align="center">
<img width="1172" height="757" alt="View_Shift_Record" src="https://github.com/user-attachments/assets/3a58cece-3b23-42da-8f4b-933be27ef239" />
  <p><em>Fig 4. Read-only audited view for historical shift reviews.</em></p>
</div>

<!-- Attendence -->
<div align="center">
<img width="1523" height="889" alt="Attendence" src="https://github.com/user-attachments/assets/b17c3982-a01f-4152-9d56-cc67ed24bfdd" />
  <p><em>Fig 5. Built-in Staff Attendance monitoring and scheduling arrays.</em></p>
</div>

<!-- LoginPage -->
<div align="center">
<img width="1919" height="968" alt="LoginPage" src="https://github.com/user-attachments/assets/2d5fd995-9c13-45b8-b8d7-588f91bbced0" />
  <p><em>Fig 6. Secure Authentication Portal with transparent frosted glass layers.</em></p>
</div>

---

*Architected & Automated by Suraj Debnath.*
