AgriVision – Wheat Disease Prediction Application
AgriVision is a full-stack web application that uses an AI model to predict diseases from images of wheat leaves. It combines a Python FastAPI backend for model inference with a React and Vite frontend featuring a modern glassmorphic interface.
Features
AI-powered wheat leaf disease prediction
FastAPI backend for image-based model inference
React + Vite frontend with a glassmorphic user interface
Pre-trained Hugging Face Vision Transformer model
Optional dataset download script for custom model training
Tech Stack
Frontend: React, Vite
Backend: Python, FastAPI, Uvicorn
Machine Learning: Hugging Face Vision Transformer
Optional custom training: PyTorch or TensorFlow
Project Structure
```text
AgriVision/
├── backend/
│   ├── main.py                 # FastAPI application
│   ├── requirements.txt        # Python dependencies
│   └── download_dataset.py     # Optional dataset download script
├── frontend/                   # React + Vite application
└── README.md
```
The dataset directory `backend/datasets/wheat_leaves/` is created by the download workflow described below.
Prerequisites
Node.js 16 or newer
Python 3.9 or newer
npm
Internet connection for the initial model download
1. Set Up the Backend
Open a terminal in the project root and navigate to the backend directory:
```bash
cd backend
```
Create a Python virtual environment:
```bash
python -m venv venv
```
Activate the environment:
Windows:
```powershell
venv\Scripts\activate
```
macOS / Linux:
```bash
source venv/bin/activate
```
Install Python dependencies:
```bash
pip install -r requirements.txt
```
Start the API server:
```bash
uvicorn main:app --reload
```
The API runs at http://localhost:8000.
Note: On first launch, the backend may download a Hugging Face Vision Transformer model (approximately 300 MB). Later starts should be faster once the model is cached.
2. Set Up the Frontend
Open a second terminal in the project root and navigate to the frontend directory:
```bash
cd frontend
```
Install dependencies:
```bash
npm install
```
Start the development server:
```bash
npm run dev
```
Open the local URL shown in your terminal, usually http://localhost:5173.
3. Download a Dataset for Custom Training (Optional)
If you want to train a separate PyTorch or TensorFlow model rather than use the pre-trained Hugging Face model:
Set up Kaggle API credentials (`kaggle.json`) following the Kaggle API instructions.
Navigate to the `backend` directory.
Run:
```bash
python download_dataset.py
```
The script is intended to download the Wheat Leaf Dataset into `backend/datasets/wheat_leaves/`, organized by disease class. Dataset availability and exact output depend on the script and Kaggle configuration.
How It Works
The user interacts with the React frontend to submit a wheat leaf image.
The frontend sends the image to the FastAPI backend.
The backend uses a Vision Transformer model to infer a disease prediction.
The application presents the prediction to the user.
Author
Abishek V — Project Developer
