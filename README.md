# AgriVision Pro — Wheat Disease Detection Web App

A full-stack wheat-leaf analysis dashboard with a React/Vite interface and a FastAPI backend. **Important: the supplied backend currently uses demo-mode, randomly generated predictions, not a loaded trained classifier.** Do not use its output for real agricultural decisions.

## Features
- Wheat leaf image upload and disease-result interface
- Dashboard, treatment information, farming tips, weather context, and chat UI
- REST API and account-related backend modules
- Responsive React frontend

## Technology
React 19, Vite, JavaScript, CSS, FastAPI, Python, Pillow, PyTorch/Transformers dependencies, SQLAlchemy.

## Layout
- `frontend/` — Vite application
- `backend/` — API, data utilities, and model handler
- `render.yaml`, `Procfile` — deployment configuration from original project
- `TECHNICAL_GUIDE.md` — original technical notes

## Local installation
Requires Python and Node.js/npm. Use two terminals from the repository root.

**Terminal 1 (backend):**
```bash
cd backend
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload
```

**Terminal 2 (frontend):**
```bash
cd frontend
npm ci
npm run dev
```
Visit the local URL printed by Vite (typically `http://localhost:5173`); backend defaults to `http://localhost:8000`. Set `VITE_API_URL` as needed (see `frontend/.env.example`).

## Model and data notes
`backend/model_handler.py` explicitly sets `MODEL_LOADED = False` and returns randomized demo predictions. The model weights and training dataset are **not included** in this archive. `backend/download_dataset.py` uses Kaggle credentials; store `kaggle.json` outside the repository. `backend/create_train_dataset.py` uses `WHEAT_DATA_DIR` or defaults to `backend/datasets/wheat_leaves` and expects input files in `test_images/`.

## Security and deployment
Set `AGRIVISION_SECRET_KEY` to a strong secret before deploying; the development fallback is **not secure**. The frontend authentication context stores credentials in browser local storage; it is not production-grade authentication. Review `render.yaml`, runtime and requirements files before deploying: they contain potentially conflicting dependency stacks.

## Screenshots
No verified application screenshots were supplied. Add screenshots under `docs/screenshots/` after running the app.

## Contributions and attribution
Jointly developed project, republished as an independent copy by **Abishek V**. Original README retained verbatim as [`ORIGINAL_README.md`](ORIGINAL_README.md) for historical attribution. No original Git commit history was included in the downloaded ZIP.

## License
No standalone license file was present in the supplied archive. Obtain agreement on licensing and distribution rights before public publication; do not assume a permissive license.
