# 🤖 Agentic AI Research Assistant

An AI-powered research assistant that autonomously analyzes documents, retrieves relevant information, and generates context-aware responses using Retrieval-Augmented Generation (RAG) and Large Language Models. The application supports multi-turn conversations, maintains chat memory, and enables users to interact with multiple research documents through an intuitive web interface.

## 🚀 Key Features

* **Document Upload** – Upload and process PDF, DOCX, and HTML documents (up to 200 MB per file).
* **Agentic Research Workflow** – The AI plans, retrieves, reasons, and generates responses based on the user's query.
* **Context-Aware Conversations** – Maintains session memory for follow-up questions and long-form discussions.
* **Semantic Search** – Uses ChromaDB for efficient vector similarity search and document retrieval.
* **Multiple LLM Support** – Switch between available language models from the interface.
* **FastAPI Backend** – RESTful APIs with interactive Swagger documentation.
* **Research-Oriented Responses** – Produces grounded answers using retrieved document context.
* **LangSmith Integration** – End-to-end tracing, debugging, and monitoring of AI workflows.

---

## 🛠 Tech Stack

* **Backend:** FastAPI, Python
* **Frontend:** Streamlit
* **AI Framework:** LangChain
* **Vector Database:** ChromaDB
* **Embeddings:** OpenAI Embeddings
* **LLM:** GPT-4o Mini (configurable)
* **Database:** SQLite
* **Monitoring:** LangSmith

---

## ⚙️ Environment Variables

Create a `.env` file in the project root:

```env
OPENAI_API_KEY=your_openai_api_key
LANGSMITH_API_KEY=your_langsmith_api_key
```

---

## 📂 Project Structure

```text
AGENTIC-AI-RESEARCH-ASSISTANT/
├── api/
│   ├── chroma_db/
│   ├── chroma_utils.py
│   ├── db_utils.py
│   ├── langchain_utils.py
│   ├── main.py
│   ├── pydantic_models.py
│   └── rag_app.db
│
├── app/
│   ├── api_utils.py
│   ├── chat_interface.py
│   ├── sidebar.py
│   └── streamlit_app.py
│
├── docs/
├── documentation/
├── README.md
├── requirements.txt
└── .env
```

---

## 🔄 System Workflow

1. Upload research documents.
2. Documents are parsed and split into semantic chunks.
3. OpenAI embeddings are generated and stored in ChromaDB.
4. The AI agent retrieves the most relevant information for the query.
5. LangChain orchestrates retrieval and reasoning.
6. The LLM generates a grounded, context-aware response.
7. Session memory preserves conversation history for future interactions.

---

## 🔌 REST API

| Endpoint      | Method | Description                               |
| ------------- | ------ | ----------------------------------------- |
| `/upload-doc` | POST   | Upload and index research documents       |
| `/chat`       | POST   | Ask questions about uploaded documents    |
| `/list-docs`  | GET    | List indexed documents                    |
| `/delete-doc` | POST   | Remove a document from the knowledge base |

---

## 🧪 Example API Usage

```python
import requests

files = {"file": open("research_paper.pdf", "rb")}
requests.post(
    "http://localhost:8000/upload-doc",
    files=files
)

payload = {
    "message": "Summarize the key findings of this paper.",
    "session_id": "research_user"
}

response = requests.post(
    "http://localhost:8000/chat",
    json=payload
)

print(response.json())
```

---

## 🏗 Architecture

```text
Research Documents
        │
        ▼
Document Loader
        │
        ▼
Text Chunking
        │
        ▼
OpenAI Embeddings
        │
        ▼
ChromaDB Vector Store
        │
        ▼
AI Agent (Retrieve + Reason)
        │
        ▼
LangChain Orchestration
        │
        ▼
Large Language Model
        │
        ▼
Context-Aware Response
        │
        ▼
Conversation Memory (SQLite)
```

---

## 📈 Future Enhancements

* Multi-agent collaboration
* Research paper citation generation
* Web search integration
* Knowledge graph support
* Research report generation
* Multi-document comparison
* Source attribution and confidence scores

---

## 🙏 Acknowledgments

* LangChain
* FastAPI
* Streamlit
* ChromaDB
* OpenAI
* LangSmith

##
