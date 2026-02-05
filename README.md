# Nirnaya - Cloud-Native Responsible Generative AI Platform

**Nirnaya** is a comprehensive Responsible AI platform designed to ensure governance, auditability, and human oversight in Generative AI workflows. Built for the Hackathon 2026, it addresses the critical need for "explainable and controllable AI" in enterprise environments.

![Nirnaya Platform](frontend/public/logo.png)

## 🌟 Core Pillars

1.  **Governance**: Enforce strict policies (PII, toxicity, sensitive topics) on every prompt and response.
2.  **Auditability**: Complete traceability of every interaction, including source documents, confidence scores, and policy checks.
3.  **Human-in-the-Loop**: Seamless workflow for human reviewers to approve, edit, or reject AI-generated content.
4.  **Explainability**: RAG-based answers with citation to specific source documents to prevent hallucinations.

<<<<<<< HEAD
## 🚀 Key Features
=======
```
┌─────────────┐
│   User      │
└──────┬──────┘
       │
       ▼
┌─────────────────────────────────────┐
│      FastAPI Application            │
│  ┌───────────────────────────────┐  │
│  │   POST /prompt                │  │
│  │   GET /audit/{id}             │  │
│  │   POST /review/{id}           │  │
│  └───────────────────────────────┘  │
└──────┬──────────────────────┬───────┘
       │                      │
       ▼                      ▼
┌─────────────┐        ┌─────────────┐
│   Chroma    │        │  Supabase   │
│ Vector Store│        │  PostgreSQL │
└─────────────┘        └─────────────┘
       │
       ▼
┌─────────────┐
│   Gemini    │
│     LLM     │
└─────────────┘
```
>>>>>>> 77ef2168a8211767bdfeeac14f59f8c8f266cdea

- **Retrieval-Augmented Generation (RAG)**: Grounded answers using local ChromaDB and Google Gemini embeddings.
- **Dual-Language Support**: Fully localized interface in **Indonesian** and **English**.
- **Smart Analytics**: Dashboard for monitoring AI acceptance rates, top keywords, and feedback distribution.
- **Context-Aware Suggestions**: Dynamic prompt suggestions based on user intent (Governance, Audit, RAG).
- **Policy Enforcement**: Real-time detection of sensitive data and policy violations.
- **Chat Management**: Pin, rename, and delete conversation history with ease.
- **Responsive Design**: Modern, mobile-friendly UI with dark mode aesthetic.

<<<<<<< HEAD
## 🛠️ Tech Stack
=======
- Python 3.10+
- Gemini API key
- Supabase account (free tier works)
>>>>>>> 77ef2168a8211767bdfeeac14f59f8c8f266cdea

### Frontend

- **Framework**: React 19 + Vite
- **Styling**: Tailwind CSS v4
- **Icons**: Lucide React
- **Routing**: React Router DOM v7
- **State Management**: React Context API

### Backend

- **API Framework**: FastAPI (Python 3.10+)
- **AI Orchestration**: LangChain
- **LLM**: Google Gemini Pro
- **Vector Store**: ChromaDB (Local Persistence)
- **Database**: Supabase (PostgreSQL) for Audit Logs

## � Prerequisites

- **Node.js** (v18 or higher)
- **Python** (v3.10 or higher)
- **Supabase Account** (for database)
- **Google Gemini API Key**

## ⚡ Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/nirnaya.git
cd nirnaya
```

### 2. Environment Setup

Create a `.env` file in the root directory:

```env
# AI Configuration
GOOGLE_API_KEY=your_gemini_api_key_here

# Database Configuration
SUPABASE_URL=your_supabase_url
SUPABASE_KEY=your_supabase_service_role_key

# Vector Store
CHROMA_PERSIST_DIRECTORY=./chroma_db
CHROMA_COLLECTION_NAME=nirnaya_collection

# App Settings
DEBUG=True
LOG_LEVEL=INFO
```

### 3. Backend Setup

```bash
# Create virtual environment
python -m venv venv

# Activate (Windows)
venv\Scripts\activate
# Activate (Mac/Linux)
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run Database Migration (Supabase)
# Execute content of database_migration.sql in Supabase SQL Editor
```

### 4. Frontend Setup

```bash
cd frontend
npm install
cd ..
```

### 5. Run the Application

This project uses `concurrently` to run both servers with one command:

```bash
npm run dev
```

- **Frontend**: http://localhost:5173
- **Backend API**: http://localhost:8000
- **API Docs**: http://localhost:8000/docs

## 🐳 Deployment Note

### Frontend

The frontend can be easily deployed to **Vercel**, **Netlify**, or **Cloudflare Pages**.

- Root Directory: `frontend`
- Build Command: `npm run build`
- Output Directory: `dist`

### Backend

Because the backend uses **local ChromaDB** (SQLite based), it requires a persistent filesystem.
**DO NOT deploy the backend to Vercel/AWS Lambda.**
Recommended platforms: **Railway**, **Render**, **Fly.io**, or **Google Cloud Run** using Docker.

## 🤝 Contributing

This project was built for the 2026 Cloud Native Hackathon. Contributions are welcome!

## 📄 License

MIT License.
