
# FlowCRM — Intelligent CRM Platform

**FlowCRM** is a modern, single‑page CRM application designed for small to medium businesses. It combines a clean Kanban pipeline, powerful client management, task tracking, and AI‑powered analytics in one intuitive interface. Built with vanilla JavaScript and a set of lightweight libraries, it runs entirely in the browser with local storage persistence — no backend required.

![FlowCRM Dashboard](screenshots/dashboard.png)

---

## ✨ Features

- **📊 Dashboard** – Real‑time metrics, funnel charts, conversion rates, and client evolution graphs.
- **📋 Kanban Pipeline** – Drag‑and‑drop stages, customisable funnels, and weighted revenue forecasts.
- **👥 Client Management** – Full CRUD with advanced filtering (status, source, owner, date ranges), bulk actions, and client timeline history.
- **✅ Task Management** – Create, complete, and delete tasks with due dates and client association.
- **🤖 AI Analytics** – Connect to any OpenAI‑compatible API (Groq, DeepSeek, OpenRouter, etc.) to run intelligent business analysis.
- **📁 Import / Export** – Import clients from CSV, JSON, XLSX, TSV, or XML; export data in CSV, JSON, or XLSX formats.
- **📈 Reports** – Detailed metrics and charts (source conversion, owner productivity, statistical summaries).
- **🌓 Dark Mode** – Toggle between light and dark themes with persistent preference.
- **⌨️ Keyboard Shortcuts** – Speed up your workflow with intuitive shortcuts.

---

## 🚀 Technologies

- **HTML5 / CSS3** – Semantic markup and custom styling with Tailwind CSS (via CDN).
- **JavaScript (ES6+)** – Vanilla JS with modular architecture.
- **Chart.js** – Interactive charts for dashboards and reports.
- **SheetJS (xlsx)** – Excel import/export support.
- **Lucide Icons** – Clean, scalable icon set.
- **LocalStorage** – Client‑side persistence for all data.

---

## 📁 Project Structure

```
FlowCRM/
├── index.html          # Single entry point (all HTML, CSS, JS embedded)
├── css/
│   └── style.css       # (Optional – currently inline, but separated for future)
├── js/
│   └── app.js          # (Optional – all logic embedded in index.html)
├── assets/             # Icons, images, etc.
├── screenshots/        # Screenshots for README
├── README.md           # This file
└── LICENSE             # MIT License
```

> **Note:** The current version is delivered as a single HTML file for simplicity. All styles and scripts are embedded, leveraging CDN libraries. The structure above is a recommendation for future modularisation.

---

## 🛠️ Installation & Usage

1. **Clone the repository**
   ```bash
   git clone https://github.com/OtavioTavaresDev/internship-aesthetic-clinic.git
   cd internship-aesthetic-clinic
   ```

2. **Open the application**
   - Simply open `index.html` in any modern web browser (Chrome, Firefox, Edge, etc.).
   - No build steps, server, or dependencies are required.

3. **Start using FlowCRM**
   - All data is stored locally in your browser’s `localStorage`.
   - Add clients, move them through the pipeline, create tasks, and explore the AI analytics.

---

## 🖥️ Screenshots

*(Add actual screenshots here)*

| Dashboard | Pipeline | Client List | AI Analytics |
|-----------|----------|-------------|--------------|
| ![Dashboard](screenshots/dashboard.png) | ![Pipeline](screenshots/pipeline.png) | ![Clients](screenshots/clients.png) | ![AI](screenshots/ai.png) |

---

## 🧭 Roadmap

- [ ] **Multi‑user support** with role‑based access (local first, optional sync).
- [ ] **Cloud sync** (Firebase / Supabase integration).
- [ ] **Email automation** (send follow‑up emails from the platform).
- [ ] **Advanced reporting** with custom date ranges and export to PDF.
- [ ] **Mobile‑first responsive redesign** for better on‑the‑go access.
- [ ] **Activity logging** with notifications.
- [ ] **API‑first architecture** to enable third‑party integrations.

---

## 🔒 Security & Privacy

- All data is stored **locally** in your browser’s `localStorage`.
- No data is sent to any external server unless you explicitly configure an AI API key.
- API keys are never stored or transmitted by the application itself — they are only used to make direct requests to the AI provider of your choice.

---

## 📄 License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Developer

**Otavio Tavares**  
[GitHub](https://github.com/OtavioTavaresDev)

Maintained by **Vorynex Tech**  
*FlowCRM* was originally developed as a portfolio project, generalised from a real‑world internship at an aesthetics clinic. All proprietary and personal data have been removed and replaced with demo data. It is intended for educational and demonstration purposes.

---

## 🙏 Acknowledgements

- [Tailwind CSS](https://tailwindcss.com/)
- [Chart.js](https://www.chartjs.org/)
- [SheetJS](https://sheetjs.com/)
- [Lucide Icons](https://lucide.dev/)
- [Inter Font](https://rsms.me/inter/)

---

## 📬 Contact

For questions, suggestions, or collaboration, please open an issue or reach out via [GitHub](https://github.com/OtavioTavaresDev).

---

**FlowCRM** — Smart CRM, Simple & Powerful.
