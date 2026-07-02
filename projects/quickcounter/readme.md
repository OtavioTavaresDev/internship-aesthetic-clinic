# QuickCounter — Client Counter Manager

**QuickCounter** is a lightweight, browser‑based tool for managing client counters and tracking client progress across multiple categories. It’s perfect for service‑based businesses that need to monitor client distribution across stages (e.g., leads, appointments, check‑ins, closures) without any backend.

![QuickCounter Dashboard](screenshots/dashboard.png)

---

## ✨ Features

- **📊 Dashboard** – See the total number of clients per counter at a glance.
- **🔢 Counter Management** – Create, edit, reorder, and delete counters.
- **👤 Client Management** – Add, edit, and delete clients, assigning them to one or multiple counters.
- **📜 History Log** – Track every action (client creation, updates, counter changes) with date filtering and deletion.
- **💾 Backup & Restore** – Export/import all data as JSON.
- **🌐 Zero Backend** – Everything runs in your browser using `localStorage`.
- **🧩 Simple & Intuitive** – Clean UI with modals, toast notifications, and responsive design.

---

## 🚀 Technologies

- HTML5 / CSS3
- Vanilla JavaScript (ES6+)
- LocalStorage (persistence)
- No external dependencies (except a modern browser)

---

## 📁 Project Structure

```
QuickCounter/
├── index.html          # Single‑file application (all code embedded)
├── screenshots/        # (optional) Screenshots for README
├── README.md           # This file
└── LICENSE             # MIT License
```

> The entire application is contained in a single `index.html` file for easy deployment and portability.

---

## 🛠️ Installation & Usage

1. **Clone or download** this repository:
   ```bash
   git clone https://github.com/OtavioTavaresDev/quickcounter.git
   cd quickcounter
   ```

2. **Open `index.html`** in any modern web browser (Chrome, Firefox, Edge, etc.).

3. **Start using QuickCounter** – all data is saved locally in your browser’s `localStorage`.

---

## 🧭 How It Works

1. **Create Counters** – Define the categories you want to track (e.g., Leads, Appointments, Check‑ins, Closed Deals).
2. **Add Clients** – Register clients and assign them to one or more counters.
3. **View Dashboard** – See the count of clients per counter instantly.
4. **Manage Clients** – Edit or delete clients, and update their counter assignments.
5. **Reorder Counters** – Change the display order using the management modal.
6. **Track History** – All actions are logged; filter by date or clear the log.

---

## 📸 Screenshots

*(Add your screenshots here)*

| Dashboard | Counters | Clients | History |
|-----------|----------|---------|---------|
| ![Dashboard](screenshots/dashboard.png) | ![Counters](screenshots/counters.png) | ![Clients](screenshots/clients.png) | ![History](screenshots/history.png) |

---

## 🔒 Privacy & Security

- All data is stored **exclusively** in your browser’s `localStorage`.
- No data is ever sent to any server.
- No API keys, tokens, or external services are required.
- You are in full control of your data.

---

## 📄 License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Developer

**Otavio Tavares**  
[GitHub](https://github.com/OtavioTavaresDev)

Maintained by **Vorynex Tech**  
*QuickCounter* was originally developed as a portfolio project, generalized from a real‑world internship at an aesthetics clinic. All proprietary and personal data have been removed and replaced with demo data. It is intended for educational and demonstration purposes.

---

## 🙏 Acknowledgements

- [Inter Font](https://rsms.me/inter/)
- Pure CSS and Vanilla JS – no frameworks needed.

---

## 📬 Contact

For questions, suggestions, or collaboration, please open an issue or reach out via [GitHub](https://github.com/OtavioTavaresDev).

---

**QuickCounter** — Simple, Smart Client Counting.
