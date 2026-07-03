```markdown
# Atlas-AI · Intelligent Search & Conversational Assistant

**Developer:** OtávioTavaresDev  
**Brand:** Vorynex Tech  
**Version:** 2.2 (General Knowledge)

Atlas-AI is a full‑featured, single‑page web application that combines **Retrieval‑Augmented Generation (RAG)** with general‑purpose conversational AI. It gives you a private, local ChatGPT‑like experience that can answer questions using your own documents (stored in IndexedDB) or fall back to its built‑in knowledge for everyday queries.

![Atlas-AI Screenshot](https://via.placeholder.com/800x400?text=Atlas-AI+Interface)

---

## ✨ Features

### 🧠 Hybrid Knowledge Engine
- **RAG (Retrieval‑Augmented Generation)** – Retrieves relevant documents from your local knowledge base and injects them into the prompt.
- **General Knowledge Mode** – When no documents match, Atlas uses the LLM’s own knowledge to answer, just like ChatGPT.
- **Multilingual** – Automatically detects Portuguese (pt‑BR) and English, responding in the same language you use.

### 🔍 Intelligent Search & Retrieval
- **Synonym expansion** and **stop‑word filtering** for better document matching.
- **Entity extraction** with configurable scoring threshold (default 50).
- Supports **full‑text search** over document names and content.

### 📄 Document Management
- Upload `.txt`, `.md`, `.json`, `.csv` files.
- **Categorisation** – assign documents to custom categories (e.g., Finance, Projects, Sample).
- **View, search, and delete** documents directly from the sidebar.
- **Deduplication** – prevents identical files from being loaded twice.

### ⚙️ Multi‑LLM Provider Support
Configure Atlas to work with your preferred AI provider:

| Provider | Supported Models |
| :--- | :--- |
| **OpenAI** | GPT‑3.5‑turbo, GPT‑4, GPT‑4‑turbo, GPT‑4o, GPT‑4o‑mini |
| **Groq** | Llama‑3.3‑70B, Llama‑3.1‑8B, Mixtral‑8x7B, Gemma2‑9B |
| **OpenRouter** | OpenAI, Anthropic, Meta Llama, and more |
| **DeepSeek** | DeepSeek‑Chat, DeepSeek‑Coder |
| **Google Gemini** | Gemini‑Pro, Gemini‑1.5‑Pro, Gemini‑1.5‑Flash |
| **Anthropic** | Claude‑3 Haiku, Sonnet, Opus |
| **Ollama** | Llama3, Mistral, CodeLlama, Phi3 |
| **LM Studio** | Local models via HTTP endpoint |
| **Custom** | Any OpenAI‑compatible endpoint |

### 🔑 API Key Rotation
- Supports up to **4 API keys** – if one hits a rate limit, the next is used automatically.
- Great for load balancing and high‑volume usage.

### 💬 Conversation Management
- **Create, rename, and delete** conversations.
- **Search** across all conversation titles and message content.
- **Edit** any message (user or assistant) – perfect for corrections.
- **Copy** assistant responses to clipboard.
- **View sources** – see which documents were used to generate a response.

### 📊 Token & Cost Tracking
- Real‑time display of **token usage** (input + output).
- **Estimated cost** based on your chosen model’s pricing.
- **Throughput** (tokens per minute) for the selected model.

### 🎨 Theme & Customisation
- **Dark / Light** theme toggle.
- Customise the **AI name** and **system prompt**.
- Adjust **temperature**, **max tokens**, and **history length**.

### 🐞 Debug Panel
- Built‑in logger that shows search queries, token counts, API calls, and cache hits.
- Toggle on/off with a single button.

---

## 🚀 Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Edge, or Safari).
- (Optional) API keys for your chosen LLM provider.

### Installation
1. Download the `Atlas-AI.html` file.
2. Open the file directly in your browser. No server or build step is required.

### First Run
1. The app automatically loads a **sample knowledge base** (fictional cloud/AI services) on first launch.
2. Click the **+ New** button in the sidebar to start a conversation.
3. Type your question and press `Enter` or click **Send**.
4. To use the AI, go to **Settings** and add your provider API keys.

---

## 📖 Usage Guide

### Setting Up the AI Assistant
1. Click the **⚙️ Settings** button in the sidebar.
2. Select your **Provider** (e.g., OpenAI, Groq, Gemini).
3. Enter your **API Key(s)** – one per line, up to 4 keys.
4. Choose a **Model**.
5. Adjust **Temperature**, **Max Tokens**, and **History Limit** as needed.
6. Optionally customise the **System Prompt** and **AI Name**.
7. Click **Save** – you’re ready to chat!

### Working with Documents
#### Uploading Files
- Click the **📎 Attach** button (next to the message input) or use **+ Add** in the Documents section.
- Select one or more files (`.txt`, `.md`, `.json`, `.csv`).
- When prompted, assign a category (or leave as “Other”).
- The document is stored in IndexedDB and indexed for search.

#### Viewing a Document
- In the Documents list, click on any document name.
- A modal opens showing the full content.

#### Deleting Documents
- Click the `✕` button next to a document to remove it.
- Use **Clear Sample** to remove all documents in the “Sample” category.
- Use **Clear All** to delete every document (including other categories).

#### Loading Structured Data (JSON)
- Click **📂 Load Sample JSON** in the sidebar.
- Upload a JSON file containing an array of objects.
- Each object will be stored as a separate document.
- Common fields like `service`, `description`, `price` are automatically parsed for better search.

### Managing Conversations
- **New Conversation** – use the **+ New** button.
- **Search Conversations** – type in the search bar above the conversation list.
- **Delete a Conversation** – click the `✕` next to any conversation.
- **Clear Messages** – use the 🧹 button in the chat header to remove all messages from the current conversation.
- **Delete Entire Conversation** – use the 🗑️ button.

### Editing Messages
- Click the **✏️ Edit** button on any message (user or assistant).
- Modify the text and save – the conversation history updates immediately.

### Copying & Viewing Sources
- Click **📋 Copy** on an assistant message to copy its text.
- Click **📚 Sources** to see which documents were used (if any) to generate that response.

---

## 🔧 Technical Details

### Architecture
- **Vanilla JavaScript** – no frameworks or external dependencies.
- **IndexedDB** – stores documents with full‑text indexing.
- **localStorage** – stores configuration, conversations, and cache.
- **CSS Variables** – enables dynamic theming.
- **Modular design** – clearly separated modules (Logger, Storage, Config, Search, RAG, etc.).

### Data Structures
```javascript
// Document stored in IndexedDB
{
  id: "sample_Cloud_Storage_Pro",
  name: "Cloud Storage Pro.json",
  category: "Sample",
  content: "{...}",       // JSON string of the original object
  keywords: ["cloud", "storage", "pro"],
  aliases: ["cloud storage", "storage pro"],
  createdAt: 1234567890
}

// Conversation stored in localStorage
{
  id: "123456_abc123",
  title: "My Conversation",
  messages: [
    { role: "user", content: "What is Data Warehouse?", timestamp: 1234567890 },
    { role: "assistant", content: "The Data Warehouse is...", metadata: { sources: ["Data Warehouse.json"] } }
  ],
  memory: {
    category: "Sample",
    entities: ["Data Warehouse"],
    usedDocs: ["sample_Data_Warehouse"]
  }
}
```

### Search & Retrieval Pipeline
1. **Normalization** – lowercasing, accent removal, punctuation stripping.
2. **Stop‑word removal** – filters common words (I, you, the, etc.).
3. **Synonym expansion** – uses a built‑in synonym map to broaden queries.
4. **Scoring** – each document is scored based on matches in:
   - Service name (100 points)
   - Aliases (90 points)
   - Category (60 points)
   - Keywords (40 points)
   - Description (20 points)
   - Features (30 points)
5. **Threshold** – only documents with a score ≥ 50 are returned.
6. **Ranking** – results are sorted by score, descending.

### Supported Export / Import
> **Note:** Atlas-AI does not have a built‑in export/import UI, but because all data is stored in **localStorage** and **IndexedDB**, you can back up your data by:
- Copying the relevant keys from localStorage (`atlas_configs`, `atlas_conversations`, `atlas_active_conv`, `atlas_cache`).
- Using the browser’s Developer Tools to export the IndexedDB database (`Atlas_KnowledgeDB`).

In future versions, a dedicated export/import feature may be added.

---

## 🛠️ Customization

### Changing the AI Name
1. Go to **Settings**.
2. Update the **AI Name** field (e.g., “Atlas”, “EVA”, “Assistant”).
3. Click **Save**.

### System Prompt
- Modify the **System Prompt** in Settings to change the assistant’s personality, tone, or behaviour.
- The default prompt includes an instruction to respond in the same language as the user.

### Theme
- Click the **🌓 Theme** button in the sidebar to toggle between **Light** and **Dark** modes.
- Your preference is saved in `localStorage`.

### Debugging
- Enable the **🐞 Debug** panel to see real‑time logs.
- The panel shows search tokenisation, API calls, cache activity, and more.

### Adding Your Own Synonym Map
- The synonym map is defined in the `SYNONYM_MAP` object in the JavaScript.
- You can extend it to improve retrieval for your specific domain.

---

## 📋 Example JSON Document
```json
{
  "service": "Cloud Storage Pro",
  "category": "Cloud",
  "description": "High‑performance object storage with global replication.",
  "price": 9.99,
  "duration": "monthly",
  "features": ["Encryption", "Versioning", "CDN"]
}
```
When uploaded, the assistant can answer questions like:
- “What is Cloud Storage Pro?”
- “How much does Cloud Storage Pro cost?”
- “Tell me about the features of Cloud Storage Pro.”

---

## ❓ FAQ

### Is my data stored online?
**No.** All data (documents, conversations, settings) are stored locally in your browser’s **localStorage** and **IndexedDB**. Nothing is sent to any server except the AI API calls you configure.

### Can I use Atlas-AI offline?
**Yes**, once the page is loaded, all non‑AI features work offline. The AI Assistant requires an internet connection to reach the API endpoints.

### What happens if I clear my browser data?
Your conversations, documents, and settings will be lost if you clear localStorage and IndexedDB. **Always export your data** (manually via Developer Tools) to keep a backup.

### Can I share my knowledge base with others?
Yes – you can share the JSON files you uploaded. Others can import them into their own instance of Atlas-AI.

### How do I reset the app?
Clear the following from your browser’s Developer Tools:
- `localStorage` keys: `atlas_configs`, `atlas_conversations`, `atlas_active_conv`, `atlas_cache`
- IndexedDB database: `Atlas_KnowledgeDB`

### Is the AI Assistant free?
The AI Assistant requires an API key from your chosen provider. Usage costs depend on the provider’s pricing (e.g., OpenAI charges per token).

### Which models support general knowledge?
All models have general knowledge. However, the quality of answers may vary. For the best results, we recommend using GPT‑4, Claude‑3 Opus, or Llama‑3‑70B.

### Can I use Atlas-AI with my own private documents?
Absolutely. Upload any text‑based files (JSON, TXT, MD, CSV) and the assistant will retrieve and use them to answer questions.

---

## 🤝 Contributing

This project is maintained by **OtávioTavaresDev** under the **Vorynex Tech** brand. Contributions, issues, and feature requests are welcome. Feel free to fork the repository and submit pull requests to improve the core logic, add new providers, or enhance the UI.

---

## 📜 License

This project is open‑source under the **MIT License**. You are free to use, modify, and distribute it for personal or commercial purposes, provided that the original copyright and permission notice are retained.

---

## 📬 Contact & Support

- **Developer:** Otávio Tavares
- **Brand:** Vorynex Tech
- For support, feature suggestions, or collaboration, please open an issue in the repository or reach out via the official Vorynex Tech channels.

---

```
