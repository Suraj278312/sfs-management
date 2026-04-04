SFS-Management-App
A modern, offline-capable dashboard web application for digitizing petrol pump daily operations, tracking fuel variances, and reconciling till cash.

⛽ Santosh Filling Station Management System

A modern, lightning-fast, offline-capable dashboard designed to digitize and automate day-to-day operations at petrol pumps.

Version Status License

📖 Overview

The Santosh Filling Station Dashboard shifts fuel filling stations away from error-prone paper ledgers into a digitized environment. Built without heavy dependencies, this system accurately reconciles hardware nozzle readings with physical cash, online payments, staff salaries, expenses, and lent credit—all in real time.

It is specifically tailored to handle dual-fuel tracking (High-Speed Diesel & Motor Spirit) and strictly monitors shift-by-shift financial variances (shortages or excesses) while mapping them to specific staff members.

✨ Key Features

🧮 Automated Reconciliation Engine: Automatically calculates exact Expected Cash by reading opening/closing nozzle meters against dynamic daily fuel rates.
💵 Advanced Financial Ledgers: Logs cash denominations, UPI/Card payments, petty expenses, staff salaries, and lent credit separately.
📶 Offline-First "Drafts": Internet down at the station? Shifts can be saved as local "Drafts" and resumed later without losing a single digit of data.
🔐 Role-Based Access Control (RBAC): "Staff" accounts are restricted to data-entry for their own shifts, while "Managers" get full access to chronological reports and user management.
📊 1-Click Export: Generate pixel-perfect, highly detailed PDFs and Excel (XLSX) spreadsheets summarizing daily operations for quick remote auditing.
🌓 Modern UI/UX: Built with Tailwind CSS, featuring full mobile responsiveness, glassmorphism, and an elegant Dark Mode.
💻 Tech Stack

Frontend:** HTML5, Tailwind CSS
Interactivity:** Vanilla JavaScript (ES6+), FontAwesome
Storage:** Browsers' Local Storage JSON API (Ready for Firebase/Firestore migration)
Libraries:**
SheetJS (xlsx) for Excel compilation
jsPDF & jsPDF-AutoTable for dynamic PDF generation
🚀 Getting Started

Since the application uses a serverless, client-centric architecture, getting it running is incredibly simple:

Clone the repository:**
git clone https://github.com/your-username/santosh-filling-station.git
Navigate to the directory:**
cd santosh-filling-station/public
Run the application: Simply open index.html in your favorite modern browser (Chrome, Firefox, Safari, Edge). Optional: Use a local server like Live Server in VS Code for hot-reloading during development.
🤝 Contributing

Contributions, issues, and feature requests are welcome!

📝 License
This project is licensed under the MIT License - see the LICENSE file for details.
