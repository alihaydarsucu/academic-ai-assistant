# 🧠 Academic AI Assistant

**An open-source, locally running AI-powered assistant** to support students and researchers during academic writing. The system offers paraphrasing, summarization, grammar checking, citation formatting, and source recommendation functionalities—all powered by local large language models (LLMs) like LLaMA 3 and Mistral.

---

## 🚀 Features

- ✍️ AI-assisted **Paraphrasing & Summarization**
- 🔎 **Grammar and Spelling Checker** using NLP tools
- 📚 **Citation Generator** supporting APA, MLA, and Chicago formats
- 🧾 **Academic Source Recommender** from a local database
- 💻 Fully **offline**, runs on local open-source LLMs (GGUF format)
- 🖥️ Frontend options: **Streamlit** or **React**
- 📦 Easily packaged with `PyInstaller`

---

## 🧩 Project Architecture

```
academic-ai-agent/
│
├── backend/ # Python (FastAPI)
│ ├── main.py # FastAPI app & endpoint router
│ │
│ ├── models/ # LLM loading and management
│ │ └── llama_loader.py
│ │
│ ├── agents/ # One file per AI task (agent)
│ │ ├── paraphrase_agent.py
│ │ ├── summary_agent.py
│ │ ├── grammar_agent.py
│ │ ├── citation_agent.py
│ │ └── source_agent.py
│ │
│ ├── utils/ # NLP & citation formatting helpers
│ │ ├── grammar_tools.py
│ │ ├── citation_formatter.py
│ │ └── text_cleaner.py
│ │
│ ├── data/ # Local academic sources DB
│ │ └── sources.db # SQLite database
| |
│ └── config.py # Model paths and constants
│
├── frontend/ # React frontend (Vite/Next.js)
│ ├── public/
│ ├── src/
│ │ ├── components/
│ │ ├── pages/
│ │ │ ├── Home.jsx
│ │ │ ├── Paraphrase.jsx
│ │ │ ├── GrammarCheck.jsx
│ │ │ ├── CitationGen.jsx
| | | ├── Summariser.jsx
│ │ │ └── Sources.jsx
│ │ ├── api/ # Axios client to FastAPI
│ │ └── App.jsx
│ └── package.json
│
├── models/ # GGUF-format local LLMs
│ └── llama-3-8b-instruct.gguf
│
├── docs/ # MkDocs documentation
├── requirements.txt
├── pyproject.toml (optional)
└── README.md
```

## 🔧 Technologies Used

| Component       | Technology                        |
| --------------- | --------------------------------- |
| AI Model        | LLaMA 3 8B Instruct (GGUF format) |
| AI Framework    | LangChain / LlamaIndex            |
| Backend         | Python (FastAPI)                  |
| Frontend        | Streamlit or React (Vite/Next.js) |
| Database        | SQLite                            |
| NLP Tools       | spaCy, NLTK, TextBlob             |
| Citation Engine | Pybtex, CSL JSON parser           |
| Packaging       | PyInstaller                       |
| Documentation   | MkDocs                            |

---

## ⚙️ Setup & Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/academic-ai-agent.git
cd academic-ai-agent
```

### 2. Install backend dependencies

```bash
cd backend
pip install -r requirements.txt
```

### 3. Download and place a GGUF model

Put your llama-3-8b-instruct.gguf or compatible .gguf model inside the models/ directory.

### 4. Run the FastAPI backend

```bash
uvicorn backend.main:app --reload
```

### 5. Run the frontend (React)

```bash
cd frontend
npm install
npm run dev
```
