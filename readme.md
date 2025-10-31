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
