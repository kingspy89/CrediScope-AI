# 🧠 CrediScope-AI

**CrediScope-AI** is a Generative AI–powered credit assessment platform that analyzes and predicts creditworthiness using advanced machine learning and large language models (LLMs). This project was developed for the **Gen AI Hackathon by Google** to demonstrate a smarter, transparent, and explainable AI-driven financial evaluation system.

---

## 🚀 Overview

Traditional credit scoring models rely on fixed criteria and often fail to capture the complexity of real-world financial behavior. CrediScope-AI combines predictive ML models with generative LLMs to provide not just a score — but an explanation and human-readable recommendations for each assessment.

Key goals:
- Produce a probabilistic credit risk prediction.
- Provide explainability (XAI) for predictions so end users can understand the "why".
- Offer generative summaries and recommendations from LLMs.
- Make the system easy to integrate via a REST API and a frontend dashboard.

---

## 🧩 Key Features

- ✅ Credit Risk Prediction — Predicts loan default probabilities using trained ML models.
- ✅ Explainable AI (XAI) — Generates human-understandable reasons behind predictions.
- ✅ Generative Summaries — Uses LLMs to create readable insights and recommendations.
- ✅ Interactive Dashboard — Frontend React app with visualizations and analysis results.
- ✅ API Integration — Backend API (FastAPI) exposing endpoints for analysis and health checks.

---

## 🧠 Tech Stack

| Layer | Technology Used |
|-------|------------------|
| Frontend | React (Vite) + TypeScript + TailwindCSS |
| Backend | Python 3 + FastAPI + Uvicorn |
| AI / ML | scikit-learn, TensorFlow (optional), OpenAI/Gemini APIs (LLMs) |
| Database | SQLite (default) / PostgreSQL (optional) |
| Visualization | Plotly / Matplotlib / Seaborn |
| Deployment | Docker / Google Cloud Platform (GCP) |

---

## 📁 Project Layout (important files)

- `backend/` — FastAPI backend, models, services, and a small launcher (`run.py`).
  - `backend/run.py` — quick-start script that launches the FastAPI server using Uvicorn.
  - `backend/requirements.txt` — Python dependencies for the backend.
  # 🧠 CrediScope-AI

  [![Python](https://img.shields.io/badge/python-3.10%2B-blue)](https://www.python.org/) [![Vite](https://img.shields.io/badge/vite-v5-green)](https://vitejs.dev/) [![License](https://img.shields.io/badge/license-MISSING-lightgrey)](LICENSE)

  **CrediScope-AI** is a Generative AI–powered credit assessment platform that analyzes and predicts creditworthiness using advanced machine learning and large language models (LLMs). This project was developed for the **Gen AI Hackathon by Google** to demonstrate a smarter, transparent, and explainable AI-driven financial evaluation system.

  ---

  ## 🚀 Overview

  Traditional credit scoring models rely on fixed criteria and often fail to capture the complexity of real-world financial behavior. CrediScope-AI combines predictive ML models with generative LLMs to provide not just a score — but an explanation and human-readable recommendations for each assessment.

  Key goals:
  - Produce a probabilistic credit risk prediction.
  - Provide explainability (XAI) for predictions so end users can understand the "why".
  - Offer generative summaries and recommendations from LLMs.
  - Make the system easy to integrate via a REST API and a frontend dashboard.

  ---

  ## 🧩 Key Features

  - ✅ Credit Risk Prediction — Predicts loan default probabilities using trained ML models.
  - ✅ Explainable AI (XAI) — Generates human-understandable reasons behind predictions.
  - ✅ Generative Summaries — Uses LLMs to create readable insights and recommendations.
  - ✅ Interactive Dashboard — Frontend React app with visualizations and analysis results.
  - ✅ API Integration — Backend API (FastAPI) exposing endpoints for analysis and health checks.

  ---

  ## 🧠 Tech Stack

  | Layer | Technology Used |
  |-------|------------------|
  | Frontend | React (Vite) + TypeScript + TailwindCSS |
  | Backend | Python 3 + FastAPI + Uvicorn |
  | AI / ML | scikit-learn, TensorFlow (optional), OpenAI/Gemini APIs (LLMs) |
  | Database | SQLite (default) / PostgreSQL (optional) |
  | Visualization | Plotly / Matplotlib / Seaborn |
  | Deployment | Docker / Google Cloud Platform (GCP) |

  ---

  ## 📁 Project Layout (important files)

  - `backend/` — FastAPI backend, models, services, and a small launcher (`run.py`).
    - `backend/run.py` — quick-start script that launches the FastAPI server using Uvicorn.
    - `backend/requirements.txt` — Python dependencies for the backend.
    - `backend/app/` — core application package (config, routes, services).
  - `frontend/` — Vite + React frontend app. Run with `npm run dev`.

  ---

  ## ⚙️ Installation & Setup

  Below are step-by-step instructions for running the backend and frontend locally on Windows PowerShell. Commands are PowerShell-friendly.

  Prerequisites:
  - Git
  - Python 3.10+ (recommended)
  - Node.js 18+ and npm / yarn
  - (Optional) Docker for containerized runs

  ### 1) Clone the repository

  ```powershell
  git clone https://github.com/kingspy89/CrediScope-AI.git
  cd CrediScope-AI
  ```

  ### 2) Backend (Python / FastAPI)

  Open a PowerShell terminal and run:

  ```powershell
  cd backend
  # Create and activate a virtual environment (PowerShell)
  python -m venv .venv
  . .\.venv\Scripts\Activate.ps1
  pip install --upgrade pip
  pip install -r requirements.txt

  # Start the API server (development):
  python run.py
  ```

  After startup you should see logs like:
  - API docs: http://localhost:<PORT>/docs
  - Health check: http://localhost:<PORT>/health

  Notes:
  - Configuration is read from `backend/app/config.py` (for example ports, debug mode, and allowed origins).
  - If you prefer using an explicit Uvicorn command, you can run:

  ```powershell
  uvicorn app.main:app --host 0.0.0.0 --port 8080 --reload
  ```

  ### 3) Frontend (Vite + React)

  Open a separate terminal and run:

  ```powershell
  cd frontend
  npm install
  npm run dev
  ```

  The frontend dev server will usually run on http://localhost:5173 (Vite default). The backend origin can be set in environment or in `backend/app/config.py` as `FRONTEND_ORIGIN`.

  ### 4) Docker (optional)

  There is a `backend/Dockerfile` included for building a containerized backend. Example quick steps:

  ```powershell
  # From repo root
  cd backend
  docker build -t crediscope-ai-backend .
  docker run -p 8080:8080 crediscope-ai-backend
  ```

  Adjust port mapping and environment variables as necessary.

  ---

  ## 🔌 API Endpoints

  Key endpoints available in the backend (see `backend/app/routes`):
  - `GET /health` — health check
  - `GET /` or `/docs` — interactive Swagger UI (FastAPI auto docs)
  - Analysis endpoints are under `routes/` (e.g., `text_analysis`, `image_analysis`, `url_analysis`). Use the API docs to explore payload shapes.

  ---

  ## 🧪 Testing

  There are minimal tests / scripts included (for example `backend/test_mcp_server.py`). To run tests you can use `pytest` if you add test dependencies. A quick manual check is:

  1. Start backend
  2. curl or hit the `/health` endpoint

  Example (PowerShell):

  ```powershell
  Invoke-WebRequest -Uri http://localhost:8080/health -UseBasicParsing
  ```

  ---

  ## ✅ Usage Examples

  - Use the frontend to submit an analysis job and view the generative summary and model explanation.
  - Or call backend endpoints directly from your application to integrate the scoring functionality.

  ---

  ## 🛡️ Security & Privacy

  - The project is a demo/prototype. Do not use as-is for production financial decisions without a full compliance, security, and fairness audit.
  - If you integrate external LLM or API keys (OpenAI / Gemini), store keys securely (env vars, secret manager) and avoid committing them to source control.

  ---

  ## 🧭 Contribution

  Contributions are welcome. Suggested workflow:

  1. Fork the repository.
  2. Create a feature branch: `git checkout -b feat/your-feature`.
  3. Add tests and update docs where appropriate.
  4. Open a PR with a clear description and screenshots if UI changes exist.

  Please follow repository conventions (code style, linting). Frontend uses ESLint and Tailwind; backend follows Python styles in `requirements.txt`.

  ---

  ## ⚖️ License & Acknowledgements

  This project was built for the Gen AI Hackathon by Google. Check the repository root for a `LICENSE` file or add one if you plan to publish.

  Thanks to all library authors whose open-source work enables this prototype.

  ---

  ## 📬 Contact

  If you have questions, issues, or want to collaborate, open an issue on the repository or contact the maintainers listed in the repo metadata.

  ---

  ## Quick summary (TL;DR)

  - Backend: `cd backend` -> create venv -> `pip install -r requirements.txt` -> `python run.py`
  - Frontend: `cd frontend` -> `npm install` -> `npm run dev`

  Enjoy exploring CrediScope-AI! 🧠

  ---

  ## ✨ Make the README more interactive

  Want the README to look more unique and interactive? A few simple additions make it feel alive:

  - Animated demo GIF (record a short interaction showing an analysis and embed it).
  - Badges (build, license, Python, npm, Docker).
  - Short runnable examples (curl and Node fetch) so visitors can try the API quickly.

  Below are concrete steps and examples you can drop into this repository.

  ### Add an animated demo GIF (recommended)

  1. Create an `assets/` folder at the repository root (or use `frontend/public/`).
  2. Place your demo GIF there (e.g., `assets/demo.gif`).

  PowerShell example to create the folder and copy a GIF you downloaded:

  ```powershell
  # from repo root
  New-Item -ItemType Directory -Path .\assets -Force
  Copy-Item -Path C:\Path\To\your-demo.gif -Destination .\assets\demo.gif
  ```

  Embed in the README (relative path works on GitHub):

  ```markdown
  ![Demo — CrediScope-AI](assets/demo.gif)
  ```

  If you prefer to hotlink a GIF hosted elsewhere, use the full URL:

  ```markdown
  ![Live demo](https://media.giphy.com/media/your-animated-demo.gif)
  ```

  Notes:
  - Avoid embedding trademarked logos (e.g., Google) without permission. If you use branded assets, ensure you have the right to display them.
  - Keep GIFs small (2–5s, <3MB) so the README loads quickly.

  ### Example badges (add to the top of README)

  ```markdown
  [![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/your/repo/actions)
  [![Docker](https://img.shields.io/badge/docker-ready-blue)](#)
  [![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)
  ```

  ### Quick API examples (try it in PowerShell or curl)

  Health check (PowerShell):

  ```powershell
  Invoke-WebRequest -Uri http://localhost:8080/health -UseBasicParsing | Select-Object -ExpandProperty Content
  ```

  Curl example (Linux/macOS or Git Bash on Windows):

  ```bash
  curl -X POST "http://localhost:8080/analyze/text" -H "Content-Type: application/json" -d '{"text":"Sample borrower information..."}'
  ```

  Node fetch example:

  ```javascript
  import fetch from 'node-fetch';

  const resp = await fetch('http://localhost:8080/analyze/text', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ text: 'Sample borrower information...' })
  });
  console.log(await resp.json());
  ```

  ### Environment variable hints (LLM keys, config)

  Add these to your environment or a `.env` file (never commit secrets):

  ```env
  OPENAI_API_KEY=sk-...
  GEMINI_API_KEY=ya29....
  DATABASE_URL=sqlite:///./data.db
  FRONTEND_ORIGIN=http://localhost:5173
  ```

  ### Optional: small demo GIF you can use for placeholders

  If you don't have a GIF ready, create a 3–5s screen recording of the frontend using your OS recorder (or a browser extension), export as GIF, and place it in `assets/demo.gif` as shown above.

  ---

  If you'd like, I can:

  - Add a small `assets/` folder and include a lightweight placeholder GIF (I won't include third-party logos).
  - Generate a sample `.env.example` with recommended variables.
  - Add a short `CONTRIBUTING.md` and `LICENSE`.

  Tell me which of the above you'd like me to do next and I'll implement it.
