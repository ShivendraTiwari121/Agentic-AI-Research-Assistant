🚀 Features
Document Upload: Supports PDF, DOCX, HTML files (200MB limit per file)
Conversational Memory: Maintains context for follow-up questions
Multiple Models: Choose between GPT-4o-mini and other model options
Vector Storage: Efficient document retrieval with ChromaDB
Interactive API: FastAPI backend with Swagger documentation
LangSmith Integration: Built-in tracing and monitoring
⚙️ Configuration
Create a .env file in the root with the following variables:

OPENAI_API_KEY=your_openai_api_key
LANGSMITH_API_KEY=your_langsmith_api_key
📦 Project Structure
RAG-CHATBOT/
├── api/                         # FastAPI backend server
│   ├── __pycache__/             # Python bytecode cache
│   ├── chroma_db/               # ChromaDB vector storage
│   ├── app.log                  # Logging file
│   ├── chroma_utils.py          # ChromaDB utilities
│   ├── db_utils.py              # Chat history & metadata DB logic
│   ├── langchain_utils.py       # LangChain RAG pipeline
│   ├── main.py                  # FastAPI entry point
│   ├── pydantic_models.py       # Request/response validation
│   └── rag_app.db               # SQLite DB
├── app/                         # Streamlit frontend
│   ├── __pycache__/             # Python bytecode cache
│   ├── api_utils.py             # FastAPI client utils
│   ├── chat_interface.py        # Chat UI
│   ├── sidebar.py               # File upload & model switch
│   └── streamlit_app.py         # Streamlit app
├── docs/                        # Sample documents
├── documentation/               # Guides & screenshots
│   ├── screenshots/             # UI screenshots
│   ├── api_reference.md         # API docs
│   └── user_guide.md            # Manual
├── .env                         # Env variables
├── .gitignore                   # Git ignore rules
├── LICENSE                      # MIT License
├── notes.txt                    # Dev notes
├── README.md                    # This file
└── requirements.txt             # Dependencies
📚 Usage Guide
📤 Upload Documents
Open the Streamlit UI
Use the sidebar to upload PDF, DOCX, or HTML files
Uploaded docs are indexed into ChromaDB
💬 Chat with Documents
Ask a question related to the uploaded content
Ask follow-up questions — context is remembered
Switch models via the sidebar dropdown
🧪 API Usage Example (Python)
import requests

# Upload a document
files = {'file': open('document.pdf', 'rb')}
upload_res = requests.post('http://localhost:8000/upload-doc', files=files)

# Chat with the document
chat_payload = {
    "message": "What is this document about?",
    "session_id": "user123"
}
chat_res = requests.post('http://localhost:8000/chat', json=chat_payload)
print(chat_res.json())
🔌 API Endpoints
Endpoint	Method	Description
/chat	POST	Chat with uploaded documents
/upload-doc	POST	Upload and index documents
/list-docs	GET	List all uploaded documents
/delete-doc	POST	Delete a specific document
🧠 Architecture Overview
Document Ingestion: Files are split into text chunks
Embedding: Text is embedded using OpenAI embeddings
Storage: Embeddings are stored in ChromaDB
Retrieval: Relevant chunks are fetched for user queries
Generation: LangChain passes context and query to LLM
Memory: Session IDs preserve conversation history
🔑 Required API Keys
OPENAI_API_KEY: Required for embeddings and completions
LANGSMITH_API_KEY: For request tracing and logging
🖼 Screenshots
Screenshots are located in:

documentation/screenshots/
🤝 Contributing
Shivendra welcome contributions!

Fork the repository
Create a feature branch
Make your changes and commit
Open a pull request
🙏 Acknowledgments
Built with LangChain
Vector storage by ChromaDB
UI by Streamlit
Backend by FastAPI
Observability via LangSmith
