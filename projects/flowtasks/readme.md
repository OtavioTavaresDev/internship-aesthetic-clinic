
# 📋 FlowTasks

**FlowTasks** is a full-featured, client-side task management application built with vanilla JavaScript. It provides a Kanban-style board system with advanced features like AI assistance, data export/import, and a customizable dashboard.

![FlowTasks Screenshot](https://via.placeholder.com/800x400?text=FlowTasks+Screenshot)

---

## ✨ Features

### 📊 Boards & Kanban
- Create multiple boards with custom colors
- Drag & drop tasks between columns
- Drag & drop columns to reorder
- Task cards with priority, due dates, tags, and checklists
- Favorites system for boards and tasks

### 📈 Dashboard
- Real-time statistics (total tasks, done, overdue, in progress)
- Productivity chart showing task creation/completion over 7 days
- Quick overview of your workflow

### 📅 Calendar View
- See all tasks organized by due date
- Visual indicators for task priority and completion status
- Easy navigation between months

### 📝 Quick Notes
- Create and edit quick notes
- Markdown support for formatting
- Persistent storage in localStorage

### 🏥 Central Dashboard
- Customizable widgets with dynamic content
- Placeholder system: `{{totalTasks}}`, `{{todayTasks}}`, `{{boardsCount}}`, `{{highPriority}}`
- Drag & drop widget reordering

### 🎯 Executive Mode
- Focus on critical and overdue tasks
- Today's agenda view
- High-level project status

### 🧠 Brain Dump
- Create multiple tasks from free text
- Automatic task extraction and creation
- Supports comma, period, and line break separation

### 🤖 AI Assistant
- Support for multiple providers:
  - **OpenAI** (ChatGPT)
  - **Groq**
  - **Google Gemini**
- Configurable model selection
- Token usage tracking and cost estimation
- Eco mode for minimal token usage
- Context upload (TXT, MD, JSON files)
- Customizable chat font and text color

### ⚙️ Settings & Customization
- Light/Dark theme
- Custom background image
- Tag management (create, edit, delete, bulk delete)
- Sidebar item management (reorder, add, remove)
- Widget management for Central Dashboard
- Application name customization

### 📤 Export / 📥 Import
- Export data in multiple formats:
  - **JSON** (full data)
  - **CSV** (tables)
  - **XML** (structured)
  - **YAML** (human-readable)
  - **TOML** (configuration)
  - **TXT** (plain text)
  - **HTML** (web page)
- Import data from JSON, XML, YAML, TOML, and TXT files
- Complete data migration between devices

### 💾 Data Storage
- All data stored in browser's **localStorage**
- No server required
- Full data persistence across sessions

---

## 🚀 Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Edge, Safari)
- Internet connection (for AI features and library loading)

### Installation

1. **Download the HTML file**
   ```bash
   curl -O https://example.com/flowtasks.html
Or save the file directly from your browser.

Open the file

Double-click flowtasks.html

Or open it in your browser: File > Open File...

Start using!

Create your first board

Add tasks

Explore the features

AI Assistant Setup
Go to the AI Assistant page (🤖 icon)

Select your provider (OpenAI, Groq, or Gemini)

Enter your API key

Choose a model

(Optional) Add context or upload a context file

Click Save Configuration

Start chatting!

📖 Usage Guide
Creating a Board
Click + New Board on the Boards page

Enter a name

Choose a color

Click Create

Adding a Task
Open a board

Click + Task

Fill in the details:

Title (required)

Description

Due Date

Priority (Low, Medium, High, Critical)

Category

Tags

Responsible person

Observations

Checklist items

Estimated/Spent time

Task color

Choose the column

Click Save

Managing Tags
Go to Settings > Manage Tags

Add new tags with name and color

Edit existing tags

Bulk delete tags using checkboxes

Exporting Data
Go to Settings

Scroll to the Export/Import section

Click any format button (JSON, CSV, XML, etc.)

The file will download automatically

Importing Data
Go to Settings

Click Import

Select a file in a supported format

The page will reload with your imported data

🔧 Technical Details
Architecture
Vanilla JavaScript: No frameworks or dependencies

localStorage: Data persistence

CSS Variables: Dynamic theming

ES6 Modules: Clean, organized code

Data Structure
javascript
{
  boards: [...],
  categories: [...],
  tags: [...],
  notes: [...],
  settings: { theme, backgroundImage },
  ia: { provider, model, apiKey, context, ... },
  appName: "FlowTasks",
  sidebarItems: [...],
  widgets: [...]
}
Supported Export Formats
JSON: Full data structure

CSV: Board, column, task, and tag information

XML: Structured with CDATA sections

YAML: Human-readable format

TOML: Configuration format

TXT: Plain text with formatted sections

HTML: Web page with all data

🛠️ Customization
Changing the Application Name
Go to Settings

Update the Application Name field

Click Save

Adding Sidebar Items
Go to Settings > Sidebar Items

Click + Add Item

Configure the label, icon, and page

Use the arrows to reorder

Custom Background Image
Go to Settings

Enter an image URL in the Background Image field

Click Apply

Click Remove to reset

Creating Widgets
Go to Settings > Central Dashboard Widgets

Click + Add Widget

Set a title and content

Use placeholders: {{totalTasks}}, {{todayTasks}}, {{boardsCount}}, {{highPriority}}

Reporting Issues
Check the browser console for errors

Note the steps to reproduce

Include your browser and version

Feature Requests
Describe the feature clearly

Explain the use case

Suggest implementation if possible

❓ FAQ
Is my data stored online?
No. All data is stored locally in your browser's localStorage. No data is sent to any server.

Can I use FlowTasks offline?
Yes, once the page is loaded, all features work offline except for the AI Assistant (which requires an internet connection to call APIs).

What happens if I clear my browser cache?
Your data will be lost if you clear localStorage. Always export your data periodically.

Can I share my boards with others?
Not directly, but you can export your data and share the file. The recipient can import it.

How do I reset the application?
Clear your browser's localStorage for this domain, or use the import/export feature to start fresh.

Is the AI Assistant free?
The AI Assistant requires an API key from your chosen provider. Usage costs depend on the provider's pricing.

