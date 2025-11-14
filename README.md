# 🚀 AI-Powered Resume–Job Matching System  
### Using CONFIT Stage-4 (Graph Distillation) + Azure GPT Extraction + Streamlit + Colab Deployment

This project is an **AI-driven resume evaluation system** that matches a candidate’s resume with a job description using:

- **CONFIT Stage-4 Graph-Distilled Model**  
- **Azure GPT-4o-mini for structured skill extraction**  
- **Streamlit UI (launched inside Colab using ngrok)**  
- **Graphviz skill graph visualization**
- **PDF upload support**
- **Missing skill detection**
- **AI-generated candidate summary**

The entire system runs from **Google Colab**, loads the **trained Stage-4 model from Google Drive**, and exposes a full web UI via **ngrok**.

---

# 📌 Features

### ✅ **1. PDF Upload for Resume / JD**
Upload real PDF resumes and job descriptions.

### ✅ **2. Azure GPT-4o-mini Skill Extraction**
GPT extracts:
- Skills
- Experience
- Education
- Industry
- Important keywords

### ✅ **3. CONFIT Stage-4 Model**
Your model performs:
- Resume embedding
- JD embedding
- Cosine similarity
- Match score
- Missing skill prediction

### 🧠 Why Stage-4?
- Faster (student model)
- Smarter (graph-distilled from Stage-3)
- Learns section relationships (skills ↔ experience ↔ education)
- Best generalization for real resumes

### ✅ **4. Missing Skill Detection**
Automatic comparison of:
```
JD skills – Resume skills
```

### ✅ **5. AI Summary Generation**
GPT writes:
- Candidate summary  
- Strengths  
- Weaknesses  
- Fit assessment  
- Recommendations  

### ✅ **6. Skill Graph Visualization (Graphviz)**
Shows:
- Resume nodes  
- JD nodes  
- Edges between matching/missing skills  

### ✅ **7. Streamlit UI (Clean & Simple)**
All features inside one dashboard.

### ✅ **8. ngrok Support**
Run Streamlit in **Colab** and access it publicly.

---

# 📁 Folder Structure

```
resume-matcher/
│
├── README.md
├── requirements.txt
├── streamlit_app.ipynb      # Main Colab Notebook (UI + Model + GPT)
│
├── assets/                  # Images for README
│   ├── architecture.png
│   ├── pipeline.png
│   ├── example_graph.png
│
├── data/
│   ├── sample_resume.pdf
│   ├── sample_jd.pdf
│
└── model/
    └── model_info.txt       # Model Drive path info
```

---

# 🔧 Installation (Local or Colab)

### **Install dependencies**
```bash
pip install -r requirements.txt
```

For Colab, packages are installed inside the notebook.

---

# ▶️ Running the Project in Colab

1. Open **streamlit_app.ipynb**
2. Run:
   - Mount Drive  
   - Install dependencies  
   - Load Stage-4 checkpoint from Google Drive  
   - Create `app.py`  
   - Start ngrok  
   - Launch Streamlit  

3. Access your public URL from ngrok:
```
https://xxxx-xx-xx-xx.ngrok-free.app
```

You now have a full **ATS-style Resume Matching System** running in the cloud.

---

# 🧠 CONFIT Pipeline (Simple Explanation)

### **Stage-1:**  
Multi-section encoder → learns resume & JD sections (skills, experience, text).

### **Stage-2:**  
Hard negative mining → improves discrimination.

### **Stage-3:**  
Graph-Aware Teacher → section-level attention + graph fusion.

### **Stage-4:**  
Graph-Distilled Student → fast, small model trained from teacher knowledge.

This project uses **Stage-4** for inference.

---

# 📊 Match Score Calculation

Model computes:
- Resume embedding → `v_r`
- JD embedding → `v_j`

Cosine similarity:
```math
sim = (v_r ⋅ v_j) / (||v_r|| × ||v_j||)
```

Converted to match percentage:
```math
match% = (sim + 1) / 2 × 100
```

---

# 📉 Missing Skill Extraction

```
Missing Skills = JD_skills - Resume_skills
```

Shown directly in the UI.

---

# 🧠 AI Summary (GPT)

GPT-4o-mini generates:

- Overall match summary  
- Profile analysis  
- Improvement suggestions  

---

# 🖼 Sample Output

(Insert your screenshots here from `/assets/screenshots`)

---

# 📘 Model Information

**Model:** CONFIT Stage-4 Graph-Distilled Student  
**Location:** Google Drive  
**Embedding Dimension:** 512  
**Backbone:** E5-base encoder  
**Graph:** Section → Section, Skill → Skill  
**Losses:** KD loss + Graph contrastive + InfoNCE  

---

# 📄 Requirements

Included in `requirements.txt`.

Run inside Colab using:

```bash
pip install -r requirements.txt
```

---

# 🤝 Contributing

Pull requests are welcome.  
For major changes, please open an issue first to discuss.

---



---

# ⭐ Author
**MS Suhel**  
AI Engineer • Resume Matching System • CONFIT Research Adaptation  
Feel free to connect on GitHub or LinkedIn.

---

# 🎉 Final Words

This repo contains a **complete ATS automation system**, powered by:

- CONFIT Stage-4  
- Azure GPT  
- Graph reasoning  
- Streamlit UI  
- PDF parsing  
- Cloud deployment via Colab + ngrok  

You now have a fully functional **industry-level resume matching engine**.

