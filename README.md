<div align="center">
  <img src="assets/Rs4Machine.png" alt="Rs4Machine Logo" width="380" />
  <h1>⟨/⟩ Translatia — Rs4Machine</h1>
  <img src="assets/translatia.gif" alt="Translatia Demo" width="100%" />
  <p><strong>Technical translation pipeline for structured content</strong></p>
  <p>Local-first translation workflow for technical documentation with terminology-aware processing.</p>
  <p>
    <a href="https://technical-article-translator.vercel.app/translatia" target="_blank"><strong>🚀 Live App</strong></a> •
    <a href="https://translatia.onrender.com/docs" target="_blank"><strong>📡 API Docs</strong></a> •
    <a href="https://github.com/raphaelmendes-dev"><strong>GitHub</strong></a>
  </p>
  <p><em>README em <a href="README.pt-BR.md">Português</a></em></p>
</div>

---

## 🎯 Overview

**Translatia** is a technical translation experiment built by **Rs4Machine** for structured documentation workflows. It focuses on preserving domain terminology while translating technical content across languages.

The project follows the same operating principles used across the RS4 Lab: clear boundaries, measurable behavior, and human oversight over critical decisions.

---

## 🏗️ Architecture

```text
translatia/
├── frontend/                        → Next.js 15 (Vercel)
│   ├── app/
│   │   └── translatia/
│   │       └── page.jsx             → Main orchestrator
│   ├── components/Translatia/
│   │   ├── Header.jsx               → Logo + chips + progress bar
│   │   ├── Toolbar.jsx              → Selectors + PDF upload + action button
│   │   ├── TextPanel.jsx            → Original and translated panels
│   │   ├── GlossaryPanel.jsx        → Technical glossary sidebar
│   │   ├── ScanOverlay.jsx          → Animated scan effect
│   │   ├── LanguageSelector.jsx     → Language dropdown
│   │   └── PdfUpload.jsx            → PDF upload → backend
│   ├── hooks/
│   │   └── useTypewriter.js         → Typewriter animation
│   ├── constants/
│   │   └── tokens.js                → Rs4Machine design tokens
│   └── styles/
│       └── translatia.css           → Keyframes + globals
└── backend/                         → Python + FastAPI (Render)
    ├── main.py                      → POST /translate + POST /upload-pdf
    ├── requirements.txt
    └── services/
        ├── translator.py            → Translation + glossary handling
        └── pdf_extractor.py         → pypdf text extraction
```

---

## ✨ Features

- PDF upload with automatic extraction
- Translation across multiple languages with a custom selector
- Technical glossary detection and terminology preservation
- Smart chunking for large documents
- One-click language swap
- Animated processing view during translation
- Real-time word and character counters
- Responsive interface built with Rs4Machine design tokens

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js 15 + React |
| Styling | CSS-in-JS + Rs4Machine design tokens |
| Backend | Python 3.11+ + FastAPI + uvicorn |
| Translation | deep-translator (Google Translator) |
| PDF | pypdf |
| Frontend Deploy | Vercel |
| Backend Deploy | Render |

---

## 🚀 Running Locally

### Backend

```powershell
cd backend
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

Create `.env` inside `backend/`:

```env
PORT=8000
```

API available at: `http://localhost:8000/docs`

### Frontend

```powershell
cd frontend
npm install
npm run dev
```

Create `.env.local` inside `frontend/`:

```env
NEXT_PUBLIC_API_URL=http://localhost:8000
```

App available at: `http://localhost:3000/translatia`

> Run both terminals at the same time.

---

## 📡 API Endpoints

| Method | Route | Description |
|---|---|---|
| GET | `/` | API status |
| POST | `/translate` | Translate text with glossary preservation |
| POST | `/upload-pdf` | Extract text from PDF |

---

## 🔑 Environment Variables

| Variable | Where | Description |
|---|---|---|
| `NEXT_PUBLIC_API_URL` | frontend `.env.local` | Backend URL |
| `PORT` | backend `.env` | uvicorn port |

---

## 📬 Contact

**Raphael Mendes**  
**AI Systems Engineer & Founder · Rs4Machine**

- 📧 [python.dev.raphael@gmail.com](mailto:python.dev.raphael@gmail.com)
- 🔗 [LinkedIn](https://www.linkedin.com/in/raphaelmendes-dev/)
- 🌐 [Portfolio](https://portfolio-modular-rs4-machine.vercel.app/)

---

⭐ Star this repository if it helped you.

*Last updated: September 2026*
