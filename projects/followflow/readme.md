# FollowFlow — Intelligent Follow-Up Manager

**FollowFlow** is a lightweight, browser‑based follow‑up and task management system designed for service‑based businesses. It helps you manage appointments, track daily reports, automate task generation, and keep your team organized — all without a backend.

![FollowFlow Dashboard](screenshots/dashboard.png)

---

## ✨ Features

- **📌 Task Management** – View today’s tasks, completed tasks, and future tasks with date filtering.
- **📅 Upcoming View** – Filter tasks by today, tomorrow, 7/15/30 days, a specific date, or overdue items.
- **✚ Appointment Registration** – Register clients, services, items, and payments. Tasks are automatically generated based on your protocols.
- **📂 Protocols** – Create service protocols with automatic follow‑up actions (days after, title, message).
- **📋 Today's Report** – View all appointments for the current day and export them in **6 formats**: JSON, CSV, XML, HTML, TSV, and TXT.
- **📊 Dashboard** – Quick metrics: today’s appointments, pending tasks, overdue tasks, and monthly client count, plus top services.
- **💾 Backup & Management** – Export/import all data as JSON, clear everything, or **delete only appointments and tasks** while keeping clients and protocols intact.
- **🌐 Zero Backend** – Everything runs in your browser using `localStorage`.
- **🧩 Bulk Actions** – Select multiple tasks and delete them at once.
- **📥 Smart Import** – Import schedules from `.txt` files with support for **ClassPass** entries and automatic price extraction.

---

## 🚀 Technologies

- HTML5 / CSS3
- Vanilla JavaScript (ES6+)
- LocalStorage (persistence)
- No external dependencies (except a modern browser)

---

## 📁 Project Structure

```
FollowFlow/
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
   git clone https://github.com/OtavioTavaresDev/internship-aesthetic-clinic.git
   cd internship-aesthetic-clinic
   ```

2. **Open `index.html`** in any modern web browser (Chrome, Firefox, Edge, etc.).

3. **Start using FollowFlow** – all data is saved locally in your browser’s `localStorage`.

---

## 🧭 How It Works

1. **Create Protocols** – Define services and their automatic follow‑up actions (e.g., “Send satisfaction message 3 days after appointment”).
2. **Register Appointments** – Select the client, service, add items/payments, and save.
3. **Tasks are auto‑generated** – Based on the protocol’s actions, tasks appear in the “Tasks” and “Upcoming” views.
4. **Manage Tasks** – Mark as done, edit, copy messages, or delete.
5. **View Today's Report** – See all appointments for the current day and export in 6 different formats.
6. **Manage Data** – Use the Backup section to export/import JSON, clear all data, or delete only appointments and tasks.

---

## 📸 Screenshots

*(Add your screenshots here)*

| Dashboard | Tasks | Upcoming | Today's Report |
|-----------|-------|----------|----------------|
| ![Dashboard](screenshots/dashboard.png) | ![Tasks](screenshots/tasks.png) | ![Upcoming](screenshots/upcoming.png) | ![Report](screenshots/report.png) |

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
*FollowFlow* was originally developed as a portfolio project, generalized from a real‑world internship at an aesthetics clinic. All proprietary and personal data have been removed and replaced with demo data. It is intended for educational and demonstration purposes.

---

## 🙏 Acknowledgements

- [Inter Font](https://rsms.me/inter/)
- Pure CSS and Vanilla JS – no frameworks needed.

---

## 📬 Contact

For questions, suggestions, or collaboration, please open an issue or reach out via [GitHub](https://github.com/OtavioTavaresDev).

---

**FollowFlow** — Smart Follow‑Up, Simple & Powerful.
