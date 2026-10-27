# 🌾 JanSeva AI: Python LangChain + FAISS + Streamlit Implementation

> **Capstone Project Group ID:** 82 | PCCOE Pune  
> **Department:** Computer Science and Engineering (AI & ML)  
> **Project Title:** Voice-Driven Multimodal RAG Assistant for Demystifying Public Documentation in Rural Governance  

---

## 📌 Architecture Overview

This directory contains the **full Python RAG implementation** featuring:
1. **Hybrid Retrieval:** FAISS dense vector similarity search (`all-MiniLM-L6-v2`) combined with BM25 lexical keyword search via LangChain `EnsembleRetriever`.
2. **LLM Generation:** Integration with `ChatGroq` (`llama-3.3-70b-versatile`) and `ChatOpenAI` (`gpt-4o-mini`).
3. **Multimodal OCR:** Ingestion of citizen identity cards and land records using `pytesseract` and `pypdf`.
4. **Streamlit Prototype:** Multi-tab interactive user interface with citizen chatbot, voice simulation, and LaTeX evaluation metric visualizations.
5. **FastAPI REST API:** Full async API server with `/chat`, `/upload`, `/metrics`, and `/tts` endpoints.

---

## 🚀 How to Run Locally

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Run the Quantitative Evaluation Metrics (Accuracy, RMSC, F1)
```bash
python evaluate_metrics.py
```

### 3. Run the Streamlit Dashboard (Port 8501)
```bash
streamlit run app.py
```
Visit: `http://localhost:8501`

### 4. Run the FastAPI Backend Server (Port 8000)
```bash
cd backend
python run.py
```
OpenAPI Docs: `http://127.0.0.1:8000/docs`
