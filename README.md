# 🤖 Automated Resume Screening System

> A comprehensive AI-powered solution that automates resume screening, skill extraction, experience quantification, and candidate ranking using advanced NLP and machine learning techniques. Built by the team at KIIT University under the guidance of Prof. Pradeep Kandula.

---

## 🧠 Project Overview

Recruiters today face the massive challenge of screening thousands of resumes, leading to time-consuming and sometimes biased hiring decisions. This project aims to solve that by automating the screening and ranking process using transformer-based NLP models, semantic analysis, and intelligent scoring mechanisms.

### 🎯 Objective

To develop a system that:
- Parses and structures resume content
- Extracts relevant skills and quantifies experience
- Compares resumes to job descriptions using semantic similarity
- Ranks candidates based on customizable weighted scoring
- Generates concise summaries of resumes to assist recruiter review

---

## 🛠️ Key Modules and Techniques Used

### 1. 📄 Resume Parsing
- **Libraries**: PyMuPDF, EasyOCR, Regex, SpaCy  
- **Purpose**: Extract text from digital and scanned resumes, then segment it into structured fields (Education, Experience, Skills, etc.)  
- **Techniques**:
  - PyMuPDF: Fast and accurate for text-based PDFs
  - EasyOCR: High accuracy for image-based resumes
  - Regex: Section-wise parsing of resume blocks
  - SpaCy NER: For extracting entities like names, organizations, and skills

### 2. 🧠 Skill Extraction and Matching
- **Models Used**: DistilBERT, SpaCy, Regex  
- **Techniques**:
  - Contextual keyword extraction using transformer embeddings
  - Semantic skill matching using cosine similarity
  - Inverse Document Frequency (IDF) scoring for weighting rare but important skills  
> ✅ Output: Skill vectors for both resumes and job descriptions, used for similarity matching

### 3. 🧾 Experience Quantification
- **Models Used**: BERT (fine-tuned for NER), Regex  
- **Workflow**:
  - Regex patterns detect employment periods (e.g., "Jan 2020 – Mar 2023")
  - BERT captures surrounding context (role, company)
  - Handles overlapping job dates and freelance gaps
  - Outputs: Total work experience in months, experience vector

### 4. 🧮 Resume Ranking Engine
- **Technique**: Weighted Cosine Similarity  
- **Weights Example**:  
  - Skills – 40%  
  - Experience – 30%  
  - Education – 20%  
  - Certifications – 10%  

```python
Final Score = 0.6 * SkillScore + 0.4 * ExperienceScore
```

> 🏆 Outputs a normalized match score (0–100%) for every candidate, allowing recruiters to rank resumes automatically.

### 5. ✂️ Resume Summarization
- **Models Used**: FLAN-T5 (CPU), BART-Large (GPU)  
- **Purpose**: Generate concise summaries of each candidate’s profile including experience, skills, and notable achievements.  
- **Example Output**:  
  > “Experienced Software Engineer with 5+ years in backend development, skilled in Python, SQL, and cloud infrastructure.”

---

## 🔁 End-to-End Workflow

Here’s a visual overview of how the Automated Resume Screener works:

![Workflow Diagram](./workflow)

---

## ⚙️ Tech Stack

### 🔧 Backend
- Python   
- Hugging Face Transformers (BERT, DistilBERT, FLAN-T5)  
- PyMuPDF, EasyOCR, Regex  

### 💻 Frontend
- React.js + Vite  
- TailwindCSS + shadcn/ui  
- Framer Motion, Lucide Icons  
- React Query + Axios  

### 🗃️ Database & Auth
- Supabase (PostgreSQL)  
- Supabase Auth (Role-based login)   

---

## 📑 Research Papers Referred

All relevant research references are stored in the [`research-papers/`](./research-papers/) folder.

| Paper Title | Institution | Techniques Used | Outcome |
|-------------|-------------|-----------------|---------|
| Resume Matching Framework | Huawei Turkey | YOLOv8, BERT | F1-score 0.93 |
| Competence Prediction | Emory University | BERT + Multi-head Attention | 73.3% Accuracy |
| Resume Parsing | Amrita University | SpaCy NER, Regex | High Accuracy |
| Personnel Selection | BRAC University | RoBERTa, DistilBERT | 85% Accuracy |
| Text Summarization | Huawei Research | BART, T5 | BART-Large best ROUGE |

---

## 🧪 Testing and Evaluation

- Unit tests for parsing, extraction, and matching  
- Benchmark testing with real-world resume datasets  
- Visualization of similarity scores and summary validation  
- Evaluation Metrics: **Precision**, **Recall**, **F1-score**

---

## 🚀 How to Run the Project

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/automated-resume-screening.git
cd automated-resume-screening
```

### 2. Setup the Backend
```bash
python -m venv venv
source venv/bin/activate  # On Windows: .\venv\Scripts\activate
pip install -r requirements.txt
cd backend
python app.py
```

### 3. Setup the Frontend
```bash
cd frontend
npm install
npm run dev
```

## 📜 License

This project is licensed under the **MIT License**. See `LICENSE` for more details.

 
