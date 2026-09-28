<div align="center">
  <img src="assets/Rs4Machine.png" alt="Rs4Machine Logo" width="380" />
  <h1>⟨/⟩ Translatia — Rs4Machine</h1>
  <img src="assets/translatia.gif" alt="Translatia Demo" width="100%" />
  <p><strong>Pipeline técnica de tradução para conteúdo estruturado</strong></p>
  <p>Fluxo de tradução orientado a documentação técnica com preservação de terminologia.</p>
  <p>
    <a href="https://technical-article-translator.vercel.app/translatia" target="_blank"><strong>🚀 App Online</strong></a> •
    <a href="https://translatia.onrender.com/docs" target="_blank"><strong>📡 API Docs</strong></a> •
    <a href="https://github.com/raphaelmendes-dev"><strong>GitHub</strong></a>
  </p>
  <p><em>README em <a href="README.md">English</a></em></p>
</div>

---

## 🎯 Visão Geral

O **Translatia** é um experimento de tradução técnica desenvolvido pela **Rs4Machine** para fluxos de documentação estruturada. O foco está em preservar terminologia de domínio enquanto traduz conteúdo técnico entre idiomas.

O projeto segue os mesmos princípios operacionais do RS4 Lab: limites claros, comportamento mensurável e supervisão humana sobre decisões críticas.

---

## 🏗️ Arquitetura

```text
translatia/
├── frontend/                        → Next.js 15 (Vercel)
│   ├── app/
│   │   └── translatia/
│   │       └── page.jsx             → Orquestrador principal
│   ├── components/Translatia/
│   │   ├── Header.jsx               → Logo + chips + barra de progresso
│   │   ├── Toolbar.jsx              → Seletores + upload de PDF + ação
│   │   ├── TextPanel.jsx            → Painéis original e traduzido
│   │   ├── GlossaryPanel.jsx        → Sidebar do glossário técnico
│   │   ├── ScanOverlay.jsx          → Efeito de scan animado
│   │   ├── LanguageSelector.jsx     → Dropdown de idiomas
│   │   └── PdfUpload.jsx            → Upload PDF → backend
│   ├── hooks/
│   │   └── useTypewriter.js         → Animação typewriter
│   ├── constants/
│   │   └── tokens.js                → Tokens de design Rs4Machine
│   └── styles/
│       └── translatia.css           → Keyframes + globals
└── backend/                         → Python + FastAPI (Render)
    ├── main.py                      → POST /translate + POST /upload-pdf
    ├── requirements.txt
    └── services/
        ├── translator.py            → Tradução + glossário
        └── pdf_extractor.py         → Extração de texto com pypdf
```

---

## ✨ Funcionalidades

- Upload de PDF com extração automática
- Tradução entre múltiplos idiomas com seletor customizado
- Detecção de glossário técnico e preservação de terminologia
- Chunking inteligente para documentos grandes
- Troca de idiomas em um clique
- Visão de processamento animada durante a tradução
- Contadores de palavras e caracteres em tempo real
- Interface responsiva com tokens de design da Rs4Machine

---

## 🛠️ Stack Técnica

| Camada | Tecnologia |
|---|---|
| Frontend | Next.js 15 + React |
| Estilo | CSS-in-JS + tokens de design da Rs4Machine |
| Backend | Python 3.11+ + FastAPI + uvicorn |
| Tradução | deep-translator (Google Translator) |
| PDF | pypdf |
| Deploy Frontend | Vercel |
| Deploy Backend | Render |

---

## 🚀 Como Rodar Localmente

### Backend

```powershell
cd backend
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

Crie o arquivo `.env` na pasta `backend/`:

```env
PORT=8000
```

API disponível em: `http://localhost:8000/docs`

### Frontend

```powershell
cd frontend
npm install
npm run dev
```

Crie o arquivo `.env.local` na pasta `frontend/`:

```env
NEXT_PUBLIC_API_URL=http://localhost:8000
```

App disponível em: `http://localhost:3000/translatia`

> Rode os dois terminais ao mesmo tempo.

---

## 📡 Endpoints da API

| Método | Rota | Descrição |
|---|---|---|
| GET | `/` | Status da API |
| POST | `/translate` | Tradução de texto com preservação de glossário |
| POST | `/upload-pdf` | Extração de texto de PDF |

---

## 🔑 Variáveis de Ambiente

| Variável | Onde | Descrição |
|---|---|---|
| `NEXT_PUBLIC_API_URL` | frontend `.env.local` | URL do backend |
| `PORT` | backend `.env` | Porta do uvicorn |

---

## 📬 Contato

**Raphael Mendes**  
**AI Systems Engineer & Founder · Rs4Machine**

- 📧 [python.dev.raphael@gmail.com](mailto:python.dev.raphael@gmail.com)
- 🔗 [LinkedIn](https://www.linkedin.com/in/raphaelmendes-dev/)
- 🌐 [Portfolio](https://portfolio-modular-rs4-machine.vercel.app/)

---

⭐ Dê uma estrela se o projeto te ajudou.

*Última atualização: Setembro 2026*
