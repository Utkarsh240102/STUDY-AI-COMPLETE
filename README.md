# 🚀 StudyAI – The Ultimate AI-Powered Learning Companion  
*Transforming passive content into active learning with AI-first design*

<p align="center">
  <img src="https://img.shields.io/badge/Built_with-FastAPI-0a9396?style=flat-square&logo=fastapi&logoColor=white">
  <img src="https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square">
  <img src="https://img.shields.io/badge/AI_Integration-Gemini%20%26%20Langchain-yellow?style=flat-square&logo=openai">
  <img src="https://img.shields.io/badge/Cloud-Cloudinary%20%7C%20OAuth2%20Login-orange?style=flat-square">
  <img src="https://img.shields.io/badge/Database-SQLite%20%7C%20PostgreSQL-green?style=flat-square&logo=postgresql">
</p>

<p align="center">
  <a href="#-project-overview">Overview</a> •
  <a href="#-key-features">Features</a> •
  <a href="#-installation-guide">Installation</a> •
  <a href="#-api-endpoints">API</a> •
  <a href="#-troubleshooting">Troubleshooting</a> •
  <a href="#-contributing">Contributing</a> •
  <a href="#-license">License</a>
</p>

<div align="center">
  <h3>🎯 Transform Any Content Into Interactive Learning Materials</h3>
  <p>
    Upload PDFs, Videos, Documents → Get Flashcards, Mind Maps, Quizzes & More<br>
    <strong>Collaborative • AI-Powered • Persistent • Secure</strong>
  </p>
</div>

---

## 📋 Table of Contents

- [📚 Project Overview](#-project-overview)
- [🔍 Problem Statement](#-problem-statement-open-innovation-in-education)
- [💡 Our Solution](#-our-solution)
- [✨ Key Features](#-key-features)
- [🔧 Project Structure](#-project-structure)
- [🌟 What Makes StudyAI Different?](#-what-makes-studyai-different)
- [🚀 Installation Guide](#-installation-guide)
  - [Prerequisites](#prerequisites)
  - [Setup Instructions](#setup-instructions)
  - [Quick Start](#quick-start-one-command-setup)
- [💻 Usage Guide](#-usage-guide)
- [🛠️ Technology Stack](#️-technology-stack)
- [📡 API Endpoints](#-api-endpoints)
- [🗄️ Database Schema](#️-database-schema)
- [🐛 Troubleshooting](#-troubleshooting)
- [🚀 Development Guide](#-development-guide)
- [📊 Performance Metrics](#-performance-metrics)
- [🔒 Security Features](#-security-features)
- [🌐 Deployment Guide](#-deployment-guide)
- [📦 External Libraries & APIs](#-external-libraries-frameworks-and-apis)
- [📸 Screenshots](#-screenshots)
- [❓ FAQ](#-frequently-asked-questions-faq)
- [🤝 Contributing](#-contributing)
- [🗺️ Roadmap](#️-roadmap)
- [📄 License](#-license)
- [🙏 Acknowledgements](#-acknowledgements)
- [📞 Contact & Support](#-contact--support)

---

---

## 🎯 Quick Start (TL;DR)

```bash
# 1. Clone the repository
git clone https://github.com/your-username/Study_AI_Complete_Project-master.git
cd Study_AI_Complete_Project-master

# 2. Create virtual environment and install dependencies
python -m venv env
.\env\Scripts\Activate.ps1  # Windows PowerShell
# source env/bin/activate    # macOS/Linux
pip install -r requirements.txt
pip install langchain-text-splitters langchain-community[retrievers]

# 3. Configure .env file (add your API keys)
# - GOOGLE_CLIENT_ID & GOOGLE_CLIENT_SECRET (OAuth)
# - CLOUDINARY credentials (file storage)
# - GEMINI_API_KEY (AI features)

# 4. Initialize database
python init_db.py

# 5. Run the application
python run.py

# 6. Access at http://localhost:8000
```

### ⚡ Feature Comparison

| Feature | StudyAI | Traditional Study Tools | Other AI Tools |
|---------|---------|------------------------|----------------|
| 🧠 AI-Generated Flashcards | ✅ | ❌ | ✅ |
| 🗺️ Interactive Mind Maps | ✅ | Limited | ❌ |
| 📝 Smart Sticky Notes | ✅ | ❌ | ❌ |
| 🏆 Exam Question Predictor | ✅ | ❌ | ❌ |
| 💬 Document Q&A Chat | ✅ | ❌ | Limited |
| 📺 YouTube Video Processing | ✅ | ❌ | Limited |
| 👥 Study Groups | ✅ | Limited | ❌ |
| 🔐 Google OAuth | ✅ | Varies | Varies |
| 💾 Persistent Storage | ✅ | ❌ | Limited |
| 🔄 Content Regeneration | ✅ | ❌ | ❌ |
| 📊 Multiple File Formats | ✅ PDF, DOCX, Audio, Video | Limited | Limited |
| 🎨 Custom UI | ✅ | ✅ | ❌ |

---

---

## 📚 Project Overview

StudyAI is a comprehensive AI-powered learning platform designed to revolutionize how students interact with educational content. By leveraging advanced AI technology, StudyAI transforms static study materials into dynamic, interactive learning resources that adapt to individual learning styles. It provides secure authentication, personal document storage, and collaborative study group features, making it a complete learning ecosystem.

### 🎯 Core Capabilities

**Content Processing:**
- 📄 Documents (PDF, DOCX, TXT, CSV)
- 🖼️ Images with OCR text extraction
- 🎙️ Audio files with transcription
- 📺 YouTube videos with transcript/download
- 🌐 Web URLs with content scraping

**AI-Generated Study Materials:**
- 🧠 Flashcards with difficulty levels
- 🗺️ Mind maps with hierarchical structure
- 📝 Color-coded sticky notes
- 🏆 Exam questions with probability scores
- 🎯 Personalized learning paths
- 💬 Interactive document Q&A

**Collaboration Features:**
- 👥 Create/join study groups
- 🔑 Secure group access keys
- 📤 Share documents within groups
- 💾 Auto-save generated content
- 🔄 Sync across group members

### 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                      Frontend (HTML/CSS/JS)                  │
│              Jinja2 Templates + AJAX + Fetch API              │
└──────────────────────┬──────────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────────┐
│              FastAPI Application (main.py)                   │
│  ┌─────────────┬──────────────┬──────────────┬───────────┐ │
│  │   Auth      │  Documents   │  AI Features  │  Groups   │ │
│  │  Routes     │   Routes     │   Routes      │  Routes   │ │
│  └─────────────┴──────────────┴──────────────┴───────────┘ │
└──────────────────────┬──────────────────────────────────────┘
                       │
        ┌──────────────┼──────────────┐
        │              │              │
┌───────▼──────┐ ┌────▼─────┐ ┌─────▼──────┐
│   Database   │ │    AI    │ │  Storage   │
│   (SQLite)   │ │  Engine  │ │(Cloudinary)│
│              │ │          │ │            │
│ • Users      │ │• Gemini  │ │• Document  │
│ • Documents  │ │• Lang    │ │  Files     │
│ • Groups     │ │  Chain   │ │• Images    │
│ • Features   │ │• FAISS   │ │            │
└──────────────┘ └──────────┘ └────────────┘
```

### 💡 System Requirements

**Minimum Requirements:**
- Python 3.8+
- 4GB RAM
- 2GB free disk space
- Internet connection
- Modern web browser

**Recommended:**
- Python 3.10+
- 8GB+ RAM
- SSD storage
- Stable internet (for AI API calls)
- Chrome/Firefox/Edge (latest versions)

**API Requirements:**
- Google Cloud account (OAuth + Gemini API)
- Cloudinary account (free tier sufficient)

---

## 🔍 Problem Statement: Open Innovation in Education

The educational technology landscape faces a critical challenge: despite the abundance of digital learning tools, there remains a significant gap in solutions that can transform passive content consumption into active, personalized learning experiences. Existing tools often lack personalization, interactivity, and a unified approach to different content formats. This project addresses the need for open innovation by creating an integrated platform that empowers students to build their own learning pathways from any source material.

## 💡 Our Solution

StudyAI addresses these challenges through open innovation by:

1.  **Content Transformation:** Converting static educational materials (PDFs, videos, text) into a suite of interactive learning experiences.
2.  **Multi-modal Learning:** Supporting various learning styles through diverse content formats like flashcards, mind maps, and summaries, all generated from a single source.
3.  **Unified Platform:** Providing a complete suite of AI-powered study tools in one application, eliminating the need for multiple, disconnected services.
4.  **Secure & Collaborative:** Provides secure user authentication via Google and enables collaborative learning through study groups where documents and AI-generated materials can be shared and saved.
5.  **Accessibility:** Making advanced AI learning technology available to all students regardless of their technical background, fostering a more inclusive educational environment.

## ✨ Key Features

-   **🔐 Secure Authentication & User Accounts**: Login securely with your Google account to save your documents, track your generated content, and manage your learning materials across sessions.
-   **👥 Collaborative Study Groups**: Create or join study groups to share documents with peers. All AI-generated content (flashcards, quizzes, etc.) is automatically saved and shared within the group, fostering a collaborative learning environment.
-   **🧠 Smart Flashcards Generator**: AI-powered flashcards with adaptive difficulty levels.
-   **🗺️ Interactive Mind Map Creator**: Visualize complex topics with auto-generated mind maps.
-   **🚀 Personalized Learning Path**: Step-by-step guides tailored to your materials.
-   **📝 Smart Sticky Notes**: Color-coded notes organized by importance.
-   **🏆 Exam Booster**: Practice questions with probability scores for exam likelihood.
-   **📺 YouTube Summarizer**: Convert videos into comprehensive text summaries.
-   **💬 Document Q&A Chat**: Have interactive conversations about your uploaded documents.

## 🔧 Project Structure

```
study_ai_complete/
├── main.py                   # FastAPI main application, handles routing
├── run.py                    # Application startup script (Uvicorn)
├── functions.py              # Core AI generation logic for most features
├── youtubefunctions.py       # Functions for YouTube video processing
├── doc_qna_routes.py         # API routes for the Document Q&A feature
├── function_for_DOC_QNA.py   # Backend logic for Document Q&A
├── database.py               # SQLAlchemy models and database session setup
├── auth.py                   # Google OAuth authentication and user management
├── init_db.py                # Script to initialize the database schema
├── static/                   # Frontend static assets
│   ├── css/
│   │   ├── style.css         # Main stylesheet for the homepage
│   │   └── feature-pages.css # Styles for individual feature pages
│   └── js/
│       ├── script.js         # Main JavaScript for homepage interactions
│       └── feature-pages.js  # JS for feature pages (upload, generation)
├── templates/                # Jinja2 HTML templates
│   ├── index.html            # Homepage
│   ├── flashcards.html       # Flashcards feature page
│   ├── mindmap.html          # Mind Map feature page
│   ├── learning-path.html    # Learning Path feature page
│   ├── sticky-notes.html     # Sticky Notes feature page
│   ├── exam-booster.html     # Exam Booster feature page
│   ├── youtube-summarizer.html # YouTube Summarizer page
│   ├── doc-chat.html         # Document Q&A chat interface
│   ├── groups.html           # Study Groups listing page
│   └── group-detail.html     # Page for a specific study group
└── whisper-main/             # OpenAI Whisper integration for audio transcription
```

## 🌟 What Makes StudyAI Different?

StudyAI isn’t just another AI assistant wrapped in a UI. It’s a complete **AI-native learning ecosystem**—designed to transform *your* materials into engaging, intelligent, and shareable study experiences. Here’s how it goes beyond the competition:

---

### ✅ 1. **Collaborative Learning, Not Just Solo Use**
> 💬 "Other AI tools help individuals. We built a system for teams."

With **built-in study groups**, users don’t just consume AI outputs—they **co-create, co-learn, and co-revise**.

🛠️ **How it works:**
- Every user can join or create a group via a **secure key**.
- Uploaded files and AI-generated outputs (flashcards, mind maps, quizzes) are auto-synced to the group.
- Group members view, update, and discuss content collaboratively.

---

### ✅ 2. **Persistence: Every Output Tied to Every Input**
> 🗂️ "Other tools generate and forget. We track everything."

Every document uploaded in StudyAI is associated with its **own persistent database record** of generated and ungenerated features.

🛠️ **How it works:**
- On upload, a **UserDocument** or **GroupDocument** is created.
- AI-generated content (e.g., flashcards, mind maps) is stored as `GeneratedFeature` rows in SQL.
- If a user revisits a document, we show them:
  - ✅ What’s already generated  
  - 🟡 What’s still available to generate  
  - 🔁 Option to regenerate and compare

📌 This persistence enables:
- Smart dashboards
- Regeneration history
- Feature completeness tracking per file

---

### ✅ 3. **From Raw Uploads to Rich Outputs — Seamlessly**
> 📚 "We don’t give you pre-built content. We transform your own files."

StudyAI accepts:
- 📄 PDFs / DOCX
- 🖼️ Images with text
- 🎙️ Audio (lectures)
- 📺 YouTube videos
- 🌐 Raw text or URLs

Every type is **parsed, cleaned, and chunked** using specialized handlers (e.g., `pdfplumber`, `EasyOCR`, `Whisper`, `LangChain` loaders) for precise downstream AI generation.

---

### ✅ 4. **Beyond Summaries: YouTube + AI for Real Learning**
> 📺 "Most tools stop at the transcript. We start there."

Our **YouTube pipeline** isn’t just about transcription:
- Extracts or transcribes content
- Summarizes intelligently
- Offers:
  - Flashcards
  - Sticky Notes
  - Exam Questions
  - Document Chat (over video!)

No other summarizer offers this breadth of **interactive tools** on top of YouTube content.

---

### ✅ 5. **Context-Rich Mind Maps with True Structure**
> 🗺️ "Other mind maps are just bubbles. Ours are blueprints."

StudyAI mind maps reflect actual **concept hierarchy and flow**, with:
- 🌐 Central and satellite node structure
- 🎨 Semantic coloring and dynamic scaling
- 📌 Interactive zoom/pan UI

We use vector embeddings + keyword clustering to **prioritize and connect topics** accurately.

---

### ✅ 6. **Conversational AI on Your Documents**
> 💬 "Ask your documents anything—literally."

We built a **retrieval-augmented chatbot** that:
- Searches document chunks (FAISS + BM25)
- Builds a Gemini prompt with only **high-relevance content**
- Returns accurate, grounded answers

Works across text, scanned notes, YouTube transcripts, and more.

---

### ✅ 7. **UI That Feels Built for Students**
> 🎨 "Not just JSON on a screen—this is crafted content."

Our frontend is **highly visual and interactive**, featuring:
- Flip-style flashcards 🎴
- Node-linked mind maps 🧠
- Probability-tagged exam questions 🧪
- Color-coded sticky notes 🟩🟨🟥
- Modal-based Q&A interfaces 💬
- Study group dashboards 👥

We chose **form AND function**—a UI that makes AI outputs not only understandable but engaging.

---

### ✅ 8. **Simple. Secure. Scalable.**
> 🔐 "OAuth + JWT + Cloudinary = zero barrier, full control."

From day one:
- Google OAuth2 for login
- JWT for token-based auth
- Role-based permissions (user/admin)
- Secure upload handling via Cloudinary

No unnecessary signups. No broken sessions. Just fast, safe access.

---

### 🧠 Summary

> **StudyAI is not a feature demo. It’s a fully integrated AI learning engine.**

| Trait | Why It Stands Out |
|------|--------------------|
| ✅ AI-first design | AI isn’t an add-on—it’s the core |
| 🧩 Modular system | From raw input to structured output |
| 📌 Persistent learning | Track all features per file |
| 🧠 Interactive UX | Crafted experience, not just responses |
| 👥 Group support | Real collaboration, not just chatbots |

## 🚀 Installation Guide

### Prerequisites
-   **Python 3.8 or higher** (Recommended: Python 3.10+)
-   **pip** (Python package installer)
-   **Git** (for cloning the repository)
-   **Google Cloud Console Account** (for OAuth credentials)
-   **Cloudinary Account** (for file storage)
-   **Google AI Studio API Key** (for Gemini AI)

### Setup Instructions

#### Step 1: Clone the Repository
```bash
git clone https://github.com/your-username/Study_AI_Complete_Project-master.git
cd Study_AI_Complete_Project-master
```

#### Step 2: Create Virtual Environment
```bash
# Create virtual environment
python -m venv env

# Activate virtual environment
# On Windows (PowerShell)
.\env\Scripts\Activate.ps1

# On Windows (Command Prompt)
env\Scripts\activate.bat

# On macOS/Linux
source env/bin/activate
```

#### Step 3: Install Dependencies
```bash
# Install all required packages
pip install -r requirements.txt

# Install additional langchain dependencies
pip install langchain-text-splitters
pip install langchain-community[retrievers]
```

#### Step 4: Configure Environment Variables
Create a `.env` file in the root directory with the following configuration:

```env
# Google OAuth Configuration
GOOGLE_CLIENT_ID=your_google_client_id_here
GOOGLE_CLIENT_SECRET=your_google_client_secret_here

# Cloudinary Configuration
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
CLOUDINARY_URL=cloudinary://api_key:api_secret@cloud_name

# Security Configuration
SECRET_KEY=your_super_secret_jwt_key_change_in_production

# Database Configuration
DATABASE_URL=sqlite:///./study_ai.db

# Google Gemini API
GEMINI_API_KEY=your_gemini_api_key_here

# Optional Configuration
USER_AGENT=StudyAI/1.0
PORT=8000
DEBUG=false
```

#### Step 5: Obtain API Credentials

**Google OAuth Setup:**
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select existing one
3. Enable "Google+ API"
4. Go to "Credentials" → "Create Credentials" → "OAuth 2.0 Client ID"
5. Set application type to "Web application"
6. Add authorized redirect URIs:
   - `http://localhost:8000/auth/callback`
   - `http://127.0.0.1:8000/auth/callback`
7. Copy Client ID and Client Secret to `.env` file

**Cloudinary Setup:**
1. Sign up at [Cloudinary](https://cloudinary.com/)
2. Go to Dashboard
3. Copy Cloud Name, API Key, and API Secret
4. Add credentials to `.env` file

**Google Gemini API:**
1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Create a new API key
3. Copy the API key to `.env` file

#### Step 6: Initialize Database
```bash
python init_db.py
```

This will create the SQLite database and all necessary tables:
- `users` - User accounts and authentication
- `user_documents` - Personal uploaded documents
- `study_groups` - Study group information
- `group_memberships` - User-group relationships
- `group_documents` - Shared group documents
- `generated_features` - AI-generated content for user documents
- `group_features` - AI-generated content for group documents

#### Step 7: Run the Application
```bash
# Option 1: Using run.py (Recommended)
python run.py

# Option 2: Using uvicorn directly
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

#### Step 8: Access the Application
- **Main Application**: http://localhost:8000
- **API Documentation**: http://localhost:8000/docs
- **Alternative API Docs**: http://localhost:8000/redoc

### Quick Start (One Command Setup)
```bash
python run.py
```
The `run.py` script automatically:
- ✅ Creates necessary directories
- ✅ Checks dependencies
- ✅ Sets up environment
- ✅ Creates basic templates
- ✅ Starts the server

## 💎 Impact & Originality

| Criteria | Details |
|---------|---------|
| **AI-first Architecture** | Not a plugin, AI drives the core experience (Gemini, LangChain, FAISS) |
| **End-to-End Platform** | Upload → Generate → Save → Share → Revise, all in one place |
| **Multi-format Input Handling** | Audio, image, text, URL, YouTube supported |
| **Conversational Retrieval** | GPT-style Q&A on your own materials |
| **Group-Centric UX** | Innovates social learning inside AI platforms |

## 💻 Usage Guide

### For End Users

1.  **Sign In**: Securely log in using your Google account to access your personal dashboard.
2.  **Upload or Join**: Upload your personal study documents or create/join a study group to collaborate on shared materials.
3.  **Generate Features**: For any document, select an AI tool (e.g., Flashcards, Mind Map) to generate interactive study aids.
4.  **Learn & Collaborate**: Your generated content is automatically saved and associated with the document. Access it anytime from your dashboard or view content generated by your group members.

### Example Workflows

#### 📚 Workflow 1: Individual Study Session
```
1. Log in with Google → Dashboard
2. Upload lecture PDF → Document library
3. Click "Generate Flashcards" → Review cards
4. Click "Generate Mind Map" → Visualize concepts
5. Ask questions via Document Chat → Get instant answers
```

#### 👥 Workflow 2: Group Study
```
1. Create study group → Share group key with peers
2. Members join group → Collaborative space created
3. Upload shared notes → All members can access
4. Generate study materials → Auto-shared with group
5. Each member adds contributions → Collective learning
```

#### 📺 Workflow 3: YouTube Video Learning
```
1. Go to YouTube Summarizer → Paste video URL
2. System extracts transcript/audio → Processes content
3. Get comprehensive summary → Quick overview
4. Generate flashcards from video → Study key points
5. Ask questions about video → Interactive learning
```

### 🖥️ Code Examples

#### Using the API Programmatically

**Authentication:**
```python
import requests

# Get access token
response = requests.post("http://localhost:8000/auth/token", 
    json={"code": "google_oauth_code"})
token = response.json()["access_token"]

# Use token in requests
headers = {"Authorization": f"Bearer {token}"}
```

**Upload Document:**
```python
files = {"file": open("document.pdf", "rb")}
response = requests.post(
    "http://localhost:8000/upload",
    files=files,
    headers=headers
)
doc_id = response.json()["document_id"]
```

**Generate Flashcards:**
```python
response = requests.post(
    "http://localhost:8000/generate/flashcards",
    json={"document_id": doc_id, "num_cards": 10},
    headers=headers
)
flashcards = response.json()["flashcards"]
```

**Ask Document Question:**
```python
response = requests.post(
    "http://localhost:8000/doc-qna/ask",
    json={
        "document_id": doc_id,
        "question": "What are the main concepts?"
    },
    headers=headers
)
answer = response.json()["answer"]
```

#### JavaScript Frontend Example

```javascript
// Upload file with progress
async function uploadDocument(file) {
    const formData = new FormData();
    formData.append('file', file);
    
    const response = await fetch('/upload', {
        method: 'POST',
        headers: {
            'Authorization': `Bearer ${localStorage.getItem('token')}`
        },
        body: formData
    });
    
    return await response.json();
}

// Generate flashcards
async function generateFlashcards(docId) {
    const response = await fetch('/generate/flashcards', {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json',
            'Authorization': `Bearer ${localStorage.getItem('token')}`
        },
        body: JSON.stringify({
            document_id: docId,
            num_cards: 15
        })
    });
    
    return await response.json();
}
```

### 📖 Best Practices

#### For Content Quality
- ✅ Use clear, well-formatted documents for best AI results
- ✅ Break large documents into chapters/sections
- ✅ Include headings and subheadings in source material
- ✅ Ensure images are high-quality for OCR extraction
- ❌ Avoid heavily compressed or low-resolution PDFs
- ❌ Don't upload copyrighted material without permission

#### For Study Groups
- ✅ Set clear group names and descriptions
- ✅ Keep group keys secure and share privately
- ✅ Organize documents by topic/subject
- ✅ Communicate with group members about uploads
- ✅ Review and validate AI-generated content together
- ❌ Don't share sensitive personal information in groups

#### For AI Features
- ✅ Review and verify AI-generated content for accuracy
- ✅ Regenerate if results aren't satisfactory
- ✅ Use specific questions for Document Q&A
- ✅ Combine multiple features (flashcards + mind maps)
- ✅ Save important generated content separately
- ❌ Don't rely solely on AI without verification

---

## 🛠️ Technology Stack

### Backend Framework
- **FastAPI** - Modern, fast web framework for building APIs
- **Uvicorn** - ASGI server for running FastAPI
- **SQLAlchemy** - SQL toolkit and ORM
- **Alembic** - Database migration tool

### AI & Machine Learning
- **Google Gemini (gemini-1.5-flash)** - Large Language Model for content generation
- **LangChain** - Framework for developing LLM applications
- **LangChain Google GenAI** - Google AI integration for LangChain
- **Sentence Transformers** - Text embeddings (all-MiniLM-L6-v2)
- **FAISS** - Vector similarity search
- **BM25** - Ranking function for information retrieval
- **Whisper** - Audio transcription (optional)
- **EasyOCR** - Optical character recognition for images

### File Processing
- **PyPDF2** - PDF text extraction
- **pdfplumber** - Advanced PDF parsing
- **python-docx** - Word document processing
- **Pandas** - Data manipulation and CSV handling
- **Pillow** - Image processing
- **BeautifulSoup4** - Web scraping and HTML parsing

### YouTube Processing
- **yt-dlp** - YouTube video/audio downloading
- **youtube-transcript-api** - Extract video transcripts

### Authentication & Security
- **Authlib** - OAuth 2.0 client implementation
- **python-jose[cryptography]** - JWT token handling
- **PassLib** - Password hashing with bcrypt
- **itsdangerous** - Secure token generation

### Cloud Storage
- **Cloudinary** - Cloud-based file storage and management

### Frontend
- **Jinja2** - Template engine for HTML rendering
- **HTML/CSS/JavaScript** - Interactive user interface
- **AJAX** - Asynchronous data loading

### Database
- **SQLite** - Default database (production: PostgreSQL/MySQL)

---

## 📡 API Endpoints

### Authentication
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/auth/login` | Initiate Google OAuth login | No |
| GET | `/auth/callback` | OAuth callback handler | No |
| POST | `/auth/token` | Exchange code for access token | No |
| GET | `/auth/user` | Get current user info | Yes |
| POST | `/auth/logout` | Logout user | Yes |

### Document Management
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/upload` | Upload document | Yes |
| GET | `/documents` | Get user documents | Yes |
| GET | `/documents/{doc_id}` | Get specific document | Yes |
| DELETE | `/documents/{doc_id}` | Delete document | Yes |

### AI Features
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/generate/flashcards` | Generate flashcards | Yes |
| POST | `/generate/mindmap` | Generate mind map | Yes |
| POST | `/generate/learning-path` | Generate learning path | Yes |
| POST | `/generate/sticky-notes` | Generate sticky notes | Yes |
| POST | `/generate/exam-questions` | Generate exam questions | Yes |
| POST | `/generate/mcqs` | Generate MCQ quiz | Yes |

### YouTube Features
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/youtube/summarize` | Summarize YouTube video | Yes |
| POST | `/youtube/transcript` | Get video transcript | Yes |

### Document Q&A
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/doc-qna/upload` | Upload document for Q&A | Yes |
| POST | `/doc-qna/ask` | Ask question about document | Yes |
| GET | `/doc-qna/history` | Get chat history | Yes |
| DELETE | `/doc-qna/clear` | Clear conversation | Yes |

### Study Groups
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/groups/create` | Create study group | Yes |
| POST | `/groups/join` | Join group with key | Yes |
| GET | `/groups` | List user's groups | Yes |
| GET | `/groups/{group_id}` | Get group details | Yes |
| POST | `/groups/{group_id}/upload` | Upload to group | Yes |
| GET | `/groups/{group_id}/documents` | Get group documents | Yes |
| DELETE | `/groups/{group_id}/leave` | Leave group | Yes |

### Health Check
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/` | Home page | No |
| GET | `/health` | Health check | No |
| GET | `/docs` | API documentation | No |

---

## 🗄️ Database Schema

### Users Table
```sql
- id: Integer (Primary Key)
- email: String (Unique)
- name: String
- profile_picture: String (URL)
- created_at: DateTime
- last_login: DateTime
```

### UserDocuments Table
```sql
- id: Integer (Primary Key)
- user_id: Integer (Foreign Key → users.id)
- filename: String
- file_url: String (Cloudinary URL)
- file_type: String
- upload_date: DateTime
- file_size: Integer
```

### StudyGroups Table
```sql
- id: Integer (Primary Key)
- name: String
- description: String
- group_key: String (Unique, 8-char)
- created_by: Integer (Foreign Key → users.id)
- created_at: DateTime
```

### GroupMemberships Table
```sql
- id: Integer (Primary Key)
- group_id: Integer (Foreign Key → study_groups.id)
- user_id: Integer (Foreign Key → users.id)
- joined_at: DateTime
- role: String (member/admin)
```

### GeneratedFeatures Table
```sql
- id: Integer (Primary Key)
- document_id: Integer (Foreign Key → user_documents.id)
- feature_type: String (flashcards/mindmap/etc)
- content: JSON
- generated_at: DateTime
```

### GroupDocuments & GroupFeatures
Similar structure to UserDocuments and GeneratedFeatures but for group-shared content.

---

## 🐛 Troubleshooting

### Common Issues

#### 1. Virtual Environment Path Errors
**Error**: `Fatal error in launcher: Unable to create process using...`

**Solution**: Recreate the virtual environment
```bash
# Remove old environment
Remove-Item -Path "env" -Recurse -Force

# Create fresh environment
python -m venv env

# Activate and install dependencies
.\env\Scripts\Activate.ps1
pip install -r requirements.txt
```

#### 2. Environment Variables Not Loading
**Error**: `ValueError: GOOGLE_CLIENT_ID environment variable is required`

**Solution**: Ensure `.env` file exists and contains all required variables. The application uses `python-dotenv` to load environment variables.

#### 3. LangChain Import Errors
**Error**: `ModuleNotFoundError: No module named 'langchain.schema'`

**Solution**: Install updated langchain packages
```bash
pip install langchain-text-splitters
pip install langchain-community[retrievers]
pip install langchain-core
```

#### 4. Database Not Initialized
**Error**: Database tables don't exist

**Solution**: Run the database initialization script
```bash
python init_db.py
```

#### 5. Port Already in Use
**Error**: `[Errno 10048] Only one usage of each socket address is normally permitted`

**Solution**: Change the port in `.env` file or kill the process using port 8000
```bash
# Windows PowerShell
Get-Process -Id (Get-NetTCPConnection -LocalPort 8000).OwningProcess | Stop-Process

# Or change PORT in .env file
PORT=8080
```

#### 6. Cloudinary Upload Fails
**Error**: Upload returns 401 or connection errors

**Solution**: 
- Verify Cloudinary credentials in `.env`
- Check internet connection
- Ensure CLOUDINARY_URL format: `cloudinary://api_key:api_secret@cloud_name`

#### 7. Google OAuth Redirect Mismatch
**Error**: `redirect_uri_mismatch`

**Solution**: 
- Add exact callback URL in Google Cloud Console
- Use: `http://localhost:8000/auth/callback`
- Ensure port matches your running application

#### 8. Gemini API Quota Exceeded
**Error**: Rate limit or quota errors from Gemini

**Solution**:
- Check API quota in Google AI Studio
- Implement rate limiting in your requests
- Consider upgrading API plan

### Performance Tips

1. **CPU vs GPU**: The application runs on CPU by default. For faster embeddings, use a GPU-enabled environment.

2. **Vector Database**: FAISS indexes are cached. Clear `data/vector_db/` to rebuild indexes if documents change.

3. **Memory Usage**: Large documents may consume significant memory. Consider chunking very large files before processing.

4. **SQLite Limitations**: For production, migrate to PostgreSQL or MySQL for better concurrent access.

---

## 🚀 Development Guide

### Running in Development Mode
```bash
# Auto-reload on code changes
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

### Project Organization Best Practices

**Adding New Features:**
1. Define route in `main.py` or create new route file
2. Add AI logic in `functions.py` or dedicated module
3. Update database models in `database.py` if needed
4. Create frontend template in `templates/`
5. Add static assets in `static/`
6. Document API endpoint in README

**Database Migrations:**
```bash
# Create migration
alembic revision --autogenerate -m "description"

# Apply migration
alembic upgrade head
```

### Testing
```bash
# Manual testing via API docs
http://localhost:8000/docs

# Test specific endpoint
curl -X POST http://localhost:8000/generate/flashcards \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -F "file=@document.pdf"
```

### Environment Variables for Development
```env
DEBUG=true
LOG_LEVEL=debug
RELOAD=true
```

---

## 📊 Performance Metrics

- **Document Processing**: ~2-5 seconds for 10-page PDF
- **Flashcard Generation**: ~3-7 seconds for 1000 words
- **Mind Map Creation**: ~5-10 seconds for complex topics
- **YouTube Summarization**: ~10-30 seconds depending on video length
- **Document Q&A Response**: ~1-3 seconds per query

*Note: Times vary based on document complexity and API latency*

---

## 🔒 Security Features

- **OAuth 2.0** with Google for secure authentication
- **JWT tokens** for stateless session management
- **Password hashing** with bcrypt (for future custom auth)
- **CORS middleware** configured for security
- **SQL injection prevention** via SQLAlchemy ORM
- **File upload validation** to prevent malicious files
- **Token expiration** enforced (24-hour default)
- **Secure secret key** for JWT signing

---

## 🌐 Deployment Guide

### Deploy to Production

#### Option 1: Traditional Server (Linux)
```bash
# Install dependencies
sudo apt update
sudo apt install python3-pip python3-venv nginx

# Clone and setup
git clone <repository-url>
cd Study_AI_Complete_Project-master
python3 -m venv env
source env/bin/activate
pip install -r requirements.txt

# Create production .env file
nano .env

# Run with gunicorn
pip install gunicorn
gunicorn main:app -w 4 -k uvicorn.workers.UvicornWorker --bind 0.0.0.0:8000

# Setup as systemd service (optional)
sudo nano /etc/systemd/system/studyai.service
```

#### Option 2: Docker
```dockerfile
FROM python:3.10-slim

WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .
EXPOSE 8000

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

```bash
docker build -t studyai .
docker run -p 8000:8000 --env-file .env studyai
```

#### Option 3: Cloud Platforms
- **Heroku**: Use `Procfile` with `web: uvicorn main:app --host 0.0.0.0 --port $PORT`
- **AWS EC2**: Follow traditional server setup
- **Google Cloud Run**: Deploy as containerized application
- **Railway/Render**: Connect GitHub repo for automatic deployment

### Production Checklist
- [ ] Set `DEBUG=false` in production
- [ ] Use strong SECRET_KEY (32+ characters)
- [ ] Configure production database (PostgreSQL)
- [ ] Set up HTTPS/SSL certificate
- [ ] Configure reverse proxy (Nginx)
- [ ] Enable application monitoring
- [ ] Set up automated backups
- [ ] Configure CDN for static files
- [ ] Implement rate limiting
- [ ] Set up error logging (Sentry, etc.)

---

## 📦 External Libraries, Frameworks, and APIs

### Core Dependencies
- **Backend**: `FastAPI`, `Uvicorn`, `SQLAlchemy`, `Jinja2`, `Authlib`
- **AI & LLM**: `Google Gemini`, `LangChain`, `LangChain Google GenAI`, `LangChain Community`, `LangChain Core`
- **Machine Learning**: `Sentence Transformers`, `FAISS`, `BM25`, `Whisper` (optional)
- **File Processing**: `PyPDF2`, `pdfplumber`, `python-docx`, `Pillow`, `Pandas`, `EasyOCR`
- **YouTube**: `yt-dlp`, `youtube-transcript-api`
- **Web Scraping**: `BeautifulSoup4`, `Playwright`
- **Security**: `OAuth2`, `python-jose`, `passlib`, `itsdangerous`, `PyJWT`
- **Storage**: `Cloudinary`
- **Utilities**: `python-dotenv`, `aiofiles`, `python-multipart`

### API Services Used
- **Google Gemini API** - Natural language processing and generation
- **Google OAuth 2.0** - User authentication
- **Cloudinary API** - File storage and delivery
- **YouTube Data API** - Video information retrieval

---

## 📸 Screenshots

### Dashboard
![Dashboard](docs/screenshots/dashboard.png)
*Main dashboard showing uploaded documents and available features*

### Flashcards Generator
![Flashcards](docs/screenshots/flashcards.png)
*AI-generated flashcards from uploaded content*

### Mind Map Creator
![Mind Map](docs/screenshots/mindmap.png)
*Interactive mind map visualization*

### Document Q&A Chat
![Doc Chat](docs/screenshots/doc-chat.png)
*Conversational AI interface for document questions*

### Study Groups
![Study Groups](docs/screenshots/groups.png)
*Collaborative learning with study groups*

*Note: Add your screenshots to `docs/screenshots/` directory*

---

## ❓ Frequently Asked Questions (FAQ)

### General Questions

**Q: Is StudyAI free to use?**  
A: Yes, the application is open-source. However, you need to provide your own API keys for Google Gemini, which has free tier limits.

**Q: What file formats are supported?**  
A: PDF, DOCX, TXT, CSV, images (PNG, JPG), audio files, and YouTube URLs.

**Q: How secure is my data?**  
A: We use Google OAuth for authentication and Cloudinary for secure file storage. Files are associated with your account and not publicly accessible.

**Q: Can I use this offline?**  
A: No, StudyAI requires internet connection for AI features and cloud storage. However, you can view previously generated content offline if cached.

**Q: Is there a mobile app?**  
A: Currently, StudyAI is a web application accessible via mobile browsers. A native mobile app is on the roadmap.

### Technical Questions

**Q: Why do I need so many API keys?**  
A: Different services (authentication, AI processing, file storage) require their own credentials for security and access control.

**Q: Can I use a different database than SQLite?**  
A: Yes! Modify `DATABASE_URL` in `.env` to use PostgreSQL, MySQL, or other SQLAlchemy-supported databases.

**Q: How do I upgrade the AI model?**  
A: Change the model name in `functions.py` and other AI modules from `gemini-1.5-flash` to another Gemini model like `gemini-1.5-pro`.

**Q: Can I self-host without cloud services?**  
A: Partially. You'll still need Gemini API for AI features, but you can replace Cloudinary with local file storage by modifying `cloudinary_config.py`.

**Q: What's the maximum file size?**  
A: Default is 10MB per file. Modify in `main.py` or your cloud storage settings.

### Feature Questions

**Q: How accurate are the AI-generated flashcards?**  
A: Accuracy depends on source material quality and AI model performance. Always review generated content for accuracy.

**Q: Can I edit generated content?**  
A: Currently, content is generated as-is. Manual editing is on the roadmap. You can regenerate content with different parameters.

**Q: How many people can join a study group?**  
A: No hard limit, but performance may vary with very large groups. Recommended: 5-20 members.

**Q: Can I export generated content?**  
A: Export functionality is planned for future releases. Currently, content is stored in the database.

---

## 🤝 Contributing

We welcome contributions from the community! Here's how you can help:

### Ways to Contribute

1. **Report Bugs**: Open an issue describing the bug and steps to reproduce
2. **Suggest Features**: Share your ideas for new features or improvements
3. **Submit Pull Requests**: Fix bugs or implement new features
4. **Improve Documentation**: Help make our docs clearer and more comprehensive
5. **Share Feedback**: Let us know how you're using StudyAI

### Development Workflow

```bash
# 1. Fork the repository
# 2. Clone your fork
git clone https://github.com/your-username/Study_AI_Complete_Project-master.git

# 3. Create a feature branch
git checkout -b feature/your-feature-name

# 4. Make your changes
# 5. Test thoroughly

# 6. Commit with clear messages
git commit -m "Add: Description of your feature"

# 7. Push to your fork
git push origin feature/your-feature-name

# 8. Open a Pull Request
```

### Code Style Guidelines

- Follow PEP 8 for Python code
- Use meaningful variable and function names
- Add docstrings to functions and classes
- Comment complex logic
- Keep functions focused and modular
- Write meaningful commit messages

### Pull Request Checklist

- [ ] Code follows project style guidelines
- [ ] All tests pass (if applicable)
- [ ] Documentation updated
- [ ] No new warnings or errors
- [ ] Feature tested in local environment
- [ ] Commit messages are clear

---

## 🗺️ Roadmap

### Version 2.0 (Planned)
- [ ] Mobile-responsive design improvements
- [ ] Export features (PDF, CSV, JSON)
- [ ] Advanced analytics dashboard
- [ ] Real-time collaboration on documents
- [ ] Voice input for questions
- [ ] Multi-language support
- [ ] Custom AI model fine-tuning
- [ ] Integration with learning management systems
- [ ] Spaced repetition algorithm for flashcards
- [ ] Progress tracking and gamification

### Future Enhancements
- [ ] Native mobile apps (iOS/Android)
- [ ] Browser extensions (Chrome, Firefox)
- [ ] Integration with note-taking apps (Notion, Obsidian)
- [ ] Advanced document annotation
- [ ] Video conferencing for study groups
- [ ] Marketplace for shared study materials
- [ ] AI tutor with personalized learning paths
- [ ] Accessibility improvements (screen readers, etc.)

---

---

## 📝 Version History

### Version 1.0.0 (Current)
**Release Date:** February 2026

#### ✨ Features
- ✅ Google OAuth 2.0 authentication
- ✅ Document upload and management (PDF, DOCX, TXT, CSV, Images, Audio)
- ✅ AI-powered flashcard generation
- ✅ Interactive mind map creator
- ✅ Personalized learning paths
- ✅ Smart sticky notes with color coding
- ✅ Exam question predictor with probability scores
- ✅ YouTube video summarizer
- ✅ Document Q&A chat interface
- ✅ Study groups with collaborative features
- ✅ Cloudinary integration for file storage
- ✅ SQLite database with 7 core tables
- ✅ 30+ API endpoints
- ✅ Responsive web interface

#### 🔧 Technical Details
- FastAPI backend
- Google Gemini 1.5 Flash for AI
- LangChain framework integration
- FAISS vector search
- BM25 retrieval
- Sentence transformers for embeddings

#### 🐛 Known Issues
- Limited mobile optimization (roadmap for v2.0)
- No offline mode support
- Export features pending implementation
- Content editing requires regeneration

### Upcoming in Version 2.0
See [Roadmap](#️-roadmap) section for planned features.

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](./LICENSE) file for details.

### MIT License Summary
- ✅ Commercial use
- ✅ Modification
- ✅ Distribution
- ✅ Private use
- ❌ Liability
- ❌ Warranty

---

## 🙏 Acknowledgements

### StudyAI Development Team
- **[@Siddharthpandey20](https://github.com/Siddharthpandey20)** - Lead Developer
- **[@Utkarsh240102](https://github.com/Utkarsh240102)** - Backend & AI Integration
- **[@akhilll0305](https://github.com/akhilll0305)** - Frontend & UX Design

### Special Thanks
- Google Gemini team for accessible AI APIs
- LangChain community for excellent documentation
- FastAPI creators for the amazing framework
- All open-source contributors whose libraries power this project

### Inspiration
Built with the belief that AI should amplify human learning, not replace it. We're committed to making advanced educational technology accessible to everyone.

---

## 📞 Contact & Support

### Get Help
- **Documentation Issues**: Open an issue on GitHub
- **Feature Requests**: Submit via GitHub Issues
- **Bug Reports**: Use GitHub Issues with detailed description
- **General Questions**: Check FAQ section first

### Connect With Us
- **GitHub**: [Study_AI_Complete_Project](https://github.com/your-username/Study_AI_Complete_Project-master)
- **Email**: studyai.support@example.com (update with actual email)
- **Discord**: [Join our community](https://discord.gg/your-server) (if applicable)

### Stay Updated
- Star ⭐ this repository to receive updates
- Watch the repo for new releases
- Follow our team members on GitHub

---

## 📊 Project Statistics

![GitHub stars](https://img.shields.io/github/stars/your-username/Study_AI_Complete_Project-master?style=social)
![GitHub forks](https://img.shields.io/github/forks/your-username/Study_AI_Complete_Project-master?style=social)
![GitHub issues](https://img.shields.io/github/issues/your-username/Study_AI_Complete_Project-master)
![GitHub license](https://img.shields.io/github/license/your-username/Study_AI_Complete_Project-master)
![Python version](https://img.shields.io/badge/python-3.8%2B-blue)
![FastAPI version](https://img.shields.io/badge/fastAPI-0.100%2B-green)

### Project Metrics

| Metric | Count |
|--------|-------|
| 📝 Total Lines of Code | ~5,000+ |
| 📁 Python Files | 10+ |
| 🎨 HTML Templates | 8 |
| 🔌 API Endpoints | 30+ |
| 📦 Dependencies | 50+ |
| 🧪 Features | 8 Core Features |
| 🗄️ Database Tables | 7 |
| 🔐 Auth Methods | OAuth 2.0 + JWT |

---

<div align="center">

### 🌟 If you find StudyAI helpful, please consider giving it a star! 🌟

**Made with ❤️ and ☕ by the StudyAI Team**

*Empowering learners through AI-driven education*

[⬆ Back to Top](#-studyai--the-ultimate-ai-powered-learning-companion)

</div>