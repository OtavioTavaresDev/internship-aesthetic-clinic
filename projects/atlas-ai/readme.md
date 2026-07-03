
---

```markdown
# Atlas-AI · Intelligent Search & Conversational Assistant

**Developer:** OtávioTavaresDev  
**Brand:** Vorynex Tech  
**Version:** 2.2 (General Knowledge)

---

## 📖 Overview

**Atlas-AI** is a sophisticated, single‑page web application that combines **Retrieval‑Augmented Generation (RAG)** with general‑purpose conversational AI. It acts like a local, customizable ChatGPT that can ground its answers in your private documents (stored in IndexedDB) while still possessing general knowledge for everyday questions.

Built entirely with vanilla HTML, CSS, and JavaScript, it requires no build tools or external frameworks. It is designed for developers, researchers, and businesses who want to explore RAG pipelines, build internal knowledge assistants, or simply have a private, configurable AI interface.

---

## ✨ Key Features

- **🔍 Intelligent Search Engine** – Uses synonym expansion, stop‑word filtering, and entity extraction to retrieve the most relevant documents from your local database.
- **📄 RAG (Retrieval‑Augmented Generation)** – Injects retrieved document context into the LLM prompt, ensuring answers are grounded in your data.
- **💬 General Knowledge Mode** – If no relevant documents are found, Atlas falls back to the LLM’s built‑in knowledge, functioning like a standard ChatGPT alternative.
- **🌍 Multilingual Support** – Automatically detects Portuguese (pt‑BR) and English, responding in the same language the user asks.
- **⚙️ Multi‑LLM Provider Support** – Configured to work with:
  - OpenAI (GPT‑3.5, GPT‑4, GPT‑4o, etc.)
  - Groq (Llama, Mixtral)
  - OpenRouter
  - DeepSeek
  - Google Gemini
  - Anthropic (Claude)
  - Ollama & LM Studio (Local models)
  - Custom endpoints
- **🔑 API Key Rotation** – Handles rate limits by rotating through multiple API keys (up to 4) automatically.
- **🧠 Conversation Memory** – Stores chat history with token/cost estimation and maintains metadata (entities, used sources) per conversation.
- **📁 Document Management** – Upload, view, categorize, search, and delete documents directly from the sidebar.
- **📊 Cost & Throughput Tracking** – Displays real‑time token usage, estimated costs, and model throughput (tokens per minute).
- **🎨 Theme Toggle** – Switch between light and dark modes.
- **🐞 Debug Panel** – Built‑in logger to inspect search queries, token counts, and API interactions.

---

## 🛠️ Tech Stack

- **Frontend:** Vanilla HTML5, CSS3 (Custom Properties), JavaScript (ES6+)
- **Storage:** LocalStorage (Config/Cache) + IndexedDB (Documents)
- **API Protocol:** REST (OpenAI‑compatible)
- **Architecture:** SPA (Single Page Application), MVC pattern in the browser

---

## 🚀 Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Edge, or Safari).
- (Optional) API keys for your chosen LLM provider(s).

### Installation
1. Download the `Atlas-AI.html` file.
2. Open the file directly in your browser. No server or build step is required.
   *(For advanced use, you can serve it with any static server, e.g., `python -m http.server`).*

### First Run
1. Upon opening, the app automatically loads a sample knowledge base (fictional cloud/AI services).
2. Start a new conversation using the **+ New** button in the sidebar.
3. Type your question in the chat input and press `Enter` or click **Send**.

> **Note:** By default, no API keys are configured. To enable LLM responses, navigate to **Settings** and add your provider API keys.

---

## ⚙️ Configuration

Click the **⚙️ Settings** button in the sidebar to configure:

| Field | Description |
| :--- | :--- |
| **Provider** | Select your LLM provider (OpenAI, Groq, OpenRouter, etc.). |
| **Model** | Choose the specific model (e.g., `gpt-4o`, `llama-3.3-70b`). |
| **API URL** | Automatically filled for known providers; adjustable for custom endpoints. |
| **API Keys** | Enter one or more keys (one per line). Keys are rotated on rate‑limit errors. |
| **Temperature** | Control randomness (0.0–2.0). Lower = more deterministic. |
| **Max Tokens** | Maximum context length for the prompt. |
| **Max Docs** | Maximum number of documents to retrieve for RAG. |
| **History Limit** | Number of recent messages to send to the LLM. |
| **System Prompt** | Customize the assistant’s personality and instructions. |
| **AI Name** | The assistant’s name (used in responses). |

---

## 🧠 How It Works (Architecture)

### 1. Document Ingestion
- Users upload files (`.txt`, `.md`, `.json`, `.csv`).
- The `KnowledgeManager` extracts keywords, normalizes text, and stores the content in IndexedDB.
- A sample dataset is pre‑loaded on the first run.

### 2. Query Processing
- The user submits a message.
- `detectLanguage()` identifies whether the query is in Portuguese or English.
- `SearchEngine` expands the query with synonyms and cleans stopwords.
- It scores documents based on term frequency against the query and returns the top matches (threshold > 50).

### 3. Prompt Construction
- `PromptBuilder` constructs a system prompt that includes:
  - The user’s defined system prompt.
  - The retrieved document context (if any).
  - An instruction to use general knowledge if documents are insufficient.
  - A language directive to match the user’s input language.

### 4. LLM Inference
- `LLMClient` formats the request for the selected provider.
- It handles authentication, rate‑limit retries, and API key rotation.
- Responses are streamed back (via standard fetch) and displayed in the chat UI.

### 5. Memory & Caching
- Conversations are stored in LocalStorage.
- The most frequent question‑answer pairs are cached to reduce API costs and latency.

---

## 📂 Using Documents

### Uploading
1. Click the **📎 Attach** button or **+ Add** in the Documents section.
2. Select files from your computer.
3. Assign a category when prompted (e.g., "Finance", "Projects", "Sample").

### Viewing
- Click a document name in the sidebar to open the viewer modal with the full content.

### Deleting
- Use the `✕` button next to a document to remove it individually.
- Use **Clear Sample** or **Clear All** to batch delete.

### Loading Sample Data
- Click **📂 Load Sample JSON** to upload a custom JSON array (or object) containing your own structured data.

---

## 💬 Conversational Features

- **Edit Messages** – Click the ✏️ button on any message to correct or rephrase.
- **Copy Responses** – Use 📋 Copy to copy the assistant’s reply to your clipboard.
- **View Sources** – Click 📚 Sources to see which documents were used to generate the response.
- **Conversation Search** – Use the search bar in the sidebar to filter conversations by title or content.

---

## 🧪 Debugging

Toggle the **🐞 Debug** button in the sidebar to open the debug panel. This shows real‑time logs for:
- Search token extraction and scoring.
- Prompt token estimation.
- API requests and responses.
- Cache hits and misses.

---

## 📄 Example File Structure (JSON)

Atlas-AI accepts JSON arrays (or objects) with arbitrary fields. For RAG, it parses common fields like `service`, `description`, `price`, etc.

```json
[
  {
    "service": "Cloud Storage Pro",
    "category": "Cloud",
    "description": "High‑performance object storage.",
    "price": 9.99,
    "duration": "monthly"
  },
  {
    "service": "Vision API",
    "category": "AI/ML",
    "description": "Image recognition and analysis.",
    "price": 0.0015
  }
]
```

---

## 🤝 Contributing

This project is maintained by **OtávioTavaresDev** under the **Vorynex Tech** brand.  
Contributions, issues, and feature requests are welcome. Feel free to fork the repository and submit pull requests to improve the core logic, add new providers, or enhance the UI.

---

## 📜 License

This project is provided as open‑source under the **MIT License**.
You are free to use, modify, and distribute it for personal or commercial purposes, provided that the original copyright and permission notice are retained.

---

## 📬 Contact & Support

- **Developer:** Otávio Tavares
- **Brand:** Vorynex Tech
- For support, feature suggestions, or collaboration, please open an issue in the repository or reach out via the official Vorynex Tech channels.

---

