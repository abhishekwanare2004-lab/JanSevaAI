# 🌾 JanSeva AI: Voice-Driven Multimodal Assistant for Rural Governance

> **MDM Capstone Project Group ID:** 82  
> **Project Title:** Voice-Driven Multimodal RAG Assistant for Demystifying Public Documentation and Mitigating Exploitative Middlemen in Rural Governance  
> **Institution:** Pimpri Chinchwad College of Engineering (PCCOE), Pune  
> **Department:** Computer Science and Engineering (AI & ML) | Academic Year 2026–27  
> **Students:**  
> 1. Abhishek Wanare (123B1G111)  
> 2. Shivam Zaware (123B1G114)  
> 3. Shardool Watharkar (123B1G124)  
> **Project Guide:** Mrs. Pallavi Nikumbh | **Head of Department:** Dr. Anuradha Thakare  

---

## 📌 1. Project Overview & Objectives

Government welfare schemes and administrative paperwork in India are often written in complex jargon, making them difficult for rural citizens to understand. This information gap is routinely exploited by unauthorized middlemen (*dalals* / brokers) charging illegal fees for free services.

**JanSeva AI** solves this problem by providing:
1. **Multilingual Voice Interaction:** Speech-to-Text (STT) and synthesized voice answers (TTS) in Hindi, Marathi, and English.
2. **Conversational RAG with Context Memory:** Remembers the active scheme across turns, enabling seamless follow-up questions (e.g. *"What are the documents required for this?"*).
3. **Multimodal Document Upload & OCR:** Upload and verify land records (Khasra/Khatauni), Aadhaar cards, and ration cards.
4. **Anti-Middlemen Protections:** Alerts citizens that welfare scheme registration is **100% FREE** with Direct Benefit Transfer (DBT) directly into their bank accounts.
5. **Verifiable Transparency:** Automatic citations linking directly to official government portals (`pmkisan.gov.in`, `jansuraksha.gov.in`, `pmjay.gov.in`, `pmmvy.nic.in`).

---

## 📊 2. Quantitative Evaluation Benchmarks

Evaluated on the 137-page benchmark dataset of Indian Public Welfare and Rural Governance schemes:

| Evaluation Metric | Measured Value | Benchmark Formulation | Academic Significance |
| :--- | :---: | :--- | :--- |
| **Accuracy** | **97.50%** | $\frac{\text{TP} + \text{TN}}{\text{TP} + \text{TN} + \text{FP} + \text{FN}}$ | **39 out of 40** queries mapped correctly to exact scheme and operational eligibility. |
| **Weighted F1-Score** | **0.9743** (97.43%) | $2 \times \frac{\text{P} \times \text{R}}{\text{P} + \text{R}}$ | Harmonic mean of precision (98.02%) and recall (97.05%) across 19 categories. |
| **Macro F1-Score** | **0.9820** (98.20%) | $\frac{1}{C}\sum_{c=1}^C \text{F1}_c$ | Balanced performance across Agriculture, Health, Insurance, Women & Child. |
| **Token-Level QA F1** | **93.97%** | $\text{SQuAD Token Overlap}$ | Word-level alignment between generated guidance and official government guidelines. |
| **RMSC / RMSE (Launch Year)**| **0.2236** | $\sqrt{\frac{1}{N}\sum (\hat{y}_i - y_i)^2}$ | Root Mean Square Error on scheme launch year extraction ($\approx 0.22$ yrs deviation). |
| **Scheme Retrieval Hit Rate** | **92.50%** | $\text{Top-1 Hit Rate}$ | Top retrieved context contains exact statutory documentation. |

To recompute metrics live during review:
```bash
python evaluate_metrics.py
```

---

## 🚀 3. Quickstart: Running on Localhost

This project is built as a lightweight, zero-dependency Node.js fullstack application:

```bash
# Start the server (from project root)
npm start
# OR: node server.js
```

Open your browser:
* **Web Dashboard:** [http://localhost:8000](http://localhost:8000)
* **Metrics API:** [http://localhost:8000/metrics](http://localhost:8000/metrics)
* **Health API:** [http://localhost:8000/health](http://localhost:8000/health)

---

## 🌐 4. Cloud Deployment Guide: Vercel (Frontend) + Render (Backend)

### Step 1: Push Project to GitHub
```bash
git init
git add .
git commit -m "JanSeva AI - Capstone Group 82"
git branch -M main
git remote add origin https://github.com/<your-username>/janseva-ai.git
git push -u origin main
```

---

### Step 2: Deploy Backend to Render (Free)
1. Go to [dashboard.render.com](https://dashboard.render.com/) and click **New +** $\rightarrow$ **Web Service**.
2. Connect your GitHub repository (`janseva-ai`).
3. Set the following settings:
   * **Root Directory:** `backend`
   * **Environment:** `Node`
   * **Build Command:** *(leave blank)*
   * **Start Command:** `npm start`
   * **Instance Type:** `Free`
4. Click **Deploy Web Service**.
5. Copy your live backend URL (e.g. `https://janseva-backend.onrender.com`).

---

### Step 3: Deploy Frontend to Vercel (Free)
1. Go to [vercel.com/new](https://vercel.com/new) and import your GitHub repository (`janseva-ai`).
2. In the configuration screen:
   * **Framework Preset:** `Vite`
   * **Root Directory:** Click `Edit` and select `frontend`.
3. Expand **Environment Variables**:
   * Key: `VITE_API_BASE`
   * Value: `https://janseva-backend.onrender.com` *(your Render URL from Step 2)*
4. Click **Deploy**.
5. Done! Vercel will give you a live production frontend URL:  
   👉 `https://janseva-ai.vercel.app`

---

## 🎭 5. Recommended Live Review Demo Flow

To demonstrate all core objectives to your review panel in 3 minutes:

1. **Speech-to-Text Voice Query:**
   * Click 🎤 and speak: *"PMSBY: ₹20 में 2 लाख का दुर्घटना बीमा कैसे प्राप्त करें?"*
   * System returns the **Pradhan Mantri Suraksha Bima Yojana** overview, official portal link (`jansuraksha.gov.in`), and the **Anti-Middlemen Warning**.
2. **Text-to-Speech Playback:**
   * Click 🔊 **"Listen (आवाज़ सुनें)"** to demonstrate Hindi/English synthesized audio.
3. **Conversational Follow-Up (Context Memory):**
   * Ask: *"what are the documents required for this?"*
   * Notice that JanSeva AI identifies *"this"* as PMSBY and outputs the specific document checklist (Aadhaar, Bank Passbook, Auto-debit form).
4. **Multimodal Document Upload (OCR):**
   * Upload an Aadhaar card or land record under **"Multimodal Document OCR"** in the left sidebar.
5. **Academic Benchmarks:**
   * Click **"📊 Evaluation Metrics"** in the top navigation bar to display the Accuracy (97.50%), F1 (0.9743), and RMSC (0.2236) benchmark card.

---

## 📁 6. Directory Structure

```
GenAiProject/
├── frontend/                          # React 18 + Vite Chat Application (for Vercel)
│   ├── src/
│   │   ├── App.jsx                    # Clean chat interface with conversation memory
│   │   ├── main.jsx
│   │   └── styles.css
│   ├── public/
│   ├── index.html
│   ├── package.json
│   ├── vite.config.js
│   ├── vercel.json                    # Single-Page Application routing
│   └── .env.example                   # VITE_API_BASE configuration
│
├── backend/                           # Node.js Pure REST API Server (for Render)
│   ├── server.js                      # Context-aware RAG engine & Anti-middlemen logic
│   ├── package.json                   # "npm start"
│   ├── render.yaml                    # 1-click Render cloud blueprint
│   ├── government_schemes_dataset.json# 40 verified scheme records
│   ├── evaluate_metrics.py            # Standalone evaluation benchmark script
│   └── evaluation_metrics.json        # Precomputed benchmarks (Accuracy, F1, RMSC)
│
├── GOVT-SCHEMES-DATA/                 # Statutory scheme documentation guidelines
├── SYNOPSIS_ALIGNMENT_REPORT.md       # Capstone Section 4 & 6 mapping report
├── README.md                          # Project documentation and deployment guide
└── .gitignore                         # Git exclusion rules
```
