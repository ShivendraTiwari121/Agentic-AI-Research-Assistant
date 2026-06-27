
## 💬 Using the Chatbot

### 📁 Uploading Documents

1. Open the Streamlit interface
2. Use the **sidebar** to upload documents
3. **Supported formats**:

   * `.pdf` (PDF)
   * `.docx` (Word)
   * `.html` (Web page)
4. **File size limit**: 200MB per file
5. Documents are automatically:

   * Split into chunks
   * Embedded into the vector database (ChromaDB)

---

### 🗨️ Chatting with Documents

1. Type your question into the input field
2. Press **Enter** or click **Send**
3. View the chatbot's response in the interface
4. Ask **follow-up questions** — the bot retains context

---

### 🧠 Conversational Memory

The bot supports **contextual memory**, so:

* Follow-up questions don’t need repeated context
* It remembers prior questions and answers
* You can refer to earlier discussion naturally

**Example:**

```
You: What is this document about?
Bot: This document discusses machine learning techniques...

You: Can you give more details on the algorithms?
Bot: Based on our discussion, the algorithms include...
```

---

### 🧩 Model Selection

From the sidebar, you can:

* Choose between models (e.g., GPT-4o-mini, GPT-4)
* Adjust response settings (if supported)
* View and manage uploaded documents

---

### 📂 Managing Documents

* View uploaded files in the sidebar
* Delete any file with a click
* Upload additional files anytime
* Monitor processing status of uploads

---





### 🧾 Session Management

* Each conversation is tied to a **unique session ID**
* Sessions persist in your browser session
* Refreshing the page will clear the memory



## 💡 Tips for Best Results

### 📄 Document Preparation

* Use clear, well-structured content
* Avoid large images or tables
* Split huge docs into smaller logical files

### ❓ Question Asking

* Be specific (e.g., "Explain section 2")
* Use natural language
* Reference terms or names in the document
* Use follow-ups to dig deeper

### ⚡ Performance Optimization

* Upload in smaller batches
* Avoid huge single documents
* Refresh sessions when needed

---

Happy chatting! 🚀