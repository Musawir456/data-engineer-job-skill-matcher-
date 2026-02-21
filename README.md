# 🔍 Data Engineer Job Skill Matcher

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Open%20Source-181717?style=for-the-badge&logo=github&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

**Paste your skills. Instantly see which Data Engineer jobs you match best.**

*Built with Python, pandas & Streamlit — scraped from real Glassdoor-style job postings.*

</div>

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Demo](#-demo)
- [Tech Stack](#-tech-stack)
- [Dataset](#-dataset)
- [Project Structure](#-project-structure)
- [How the Matching Works](#-how-the-matching-works)
- [Getting Started](#-getting-started)
- [Future Improvements](#-future-improvements)
- [Author](#-author)

---

## 🧠 Overview

Job hunting as a data engineer is hard — hundreds of listings, each with a different set of required tools. This project solves that by **automatically matching your skillset to real job postings** and showing you exactly where you stand.

**What it does:**
- Cleans raw job descriptions and extracts core data engineering skills
- Compares your skills against every job and calculates an overlap score
- Shows best-matching jobs with **matched ✅** and **missing ❌** skills highlighted
- Built as an **interactive Streamlit app** for instant experimentation

**Use-cases:**
- 🎯 Find which Data Engineer jobs fit your current skillset
- 📚 Discover missing tools and technologies to learn next
- 💼 Showcase end-to-end Python + data engineering skills in your portfolio

---

## 🎬 Demo

```
Your Skills Input:
python, sql, spark, airflow, docker, aws

─────────────────────────────────────────────────
🏆 Top Match — Senior Data Engineer @ TechCorp
Score       : 5 / 7
✅ Matched  : python, sql, spark, airflow, docker
❌ Missing  : kafka, dbt
─────────────────────────────────────────────────
```

---

## 🛠 Tech Stack

| Category | Tools |
|---|---|
| **Language** | Python 3.10 |
| **Dashboard UI** | Streamlit |
| **Data Handling** | pandas, numpy |
| **Text Processing** | re (regex) |
| **EDA & Engineering** | Jupyter Notebook |
| **Version Control** | Git & GitHub |

---

## 📂 Dataset

**File:** `DataEngineer.csv` → cleaned to `data/data_engineer_jobs_clean.csv`

| Column | Description |
|---|---|
| `Job Title` | Title of the job posting |
| `Company Name` | Hiring company |
| `Location` | Job location |
| `Job Description` | Full raw job description text |
| `Rating` | Company rating |
| `Salary Estimate` | Salary range (if available) |
| `clean_desc` | *(Engineered)* Lowercased, punctuation-stripped description |
| `job_skills` | *(Engineered)* List of extracted skills per job |

---

## 🗂 Project Structure

```
data-engineer-job-skill-matcher/
│
├── app/
│   ├── 🔧 matcher.py                          # Matching logic & scoring
│   └── 🚀 streamlit_app.py                    # Streamlit UI
│
├── data/
│   └── 📊 data_engineer_jobs_clean.csv        # Cleaned dataset
│
├── 📓 01_data_engineer_skill_matcher.ipynb    # EDA + text cleaning + skill extraction
├── 📋 DataEngineer.csv                        # Raw job postings
└── 📄 README.md                               # Project documentation
```

---

## ⚙️ How the Matching Works

```
Raw Job Description
        │
        ▼
┌─────────────────────────────┐
│      Text Cleaning          │
│  • Lowercase                │
│  • Remove punctuation       │
│  • Strip extra whitespace   │
│  → stored in clean_desc     │
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────────────────────────────────┐
│              Skill Extraction                           │
│  Core skills list:                                      │
│  python • sql • spark • aws • airflow • docker • kafka  │
│  hadoop • dbt • snowflake • redshift • bigquery • etc.  │
│  → Match skills found in clean_desc → job_skills        │
└─────────────────────────────────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│     User Input (Streamlit)  │
│  "python, sql, spark, aws"  │
└─────────────────────────────┘
        │
        ▼
┌──────────────────────────────────────────┐
│           Matching & Scoring             │
│  matched_skills = user ∩ job_skills      │
│  missing_skills = job_skills − user      │
│  score = len(matched_skills)             │
│  → Sort by score (descending)            │
│  → Show Top-K jobs with gap analysis     │
└──────────────────────────────────────────┘
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Musawir456/data-engineer-job-skill-matcher-.git
cd data-engineer-job-skill-matcher-
```

### 2. Create & Activate Environment

```bash
# Using conda
conda create -n skill-matcher python=3.10 -y
conda activate skill-matcher

# Or using venv
python -m venv venv
venv\Scripts\activate       # Windows
source venv/bin/activate    # macOS/Linux
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Streamlit App

```bash
streamlit run app/streamlit_app.py
```

### 5. Open in Browser

```
http://localhost:8501
```

Enter your skills as a comma-separated list and explore your best-matching jobs! 🎯

---

## 📈 Future Improvements

- 🧠 **Smarter NLP** — Use spaCy or sentence embeddings for semantic skill matching instead of keyword overlap
- ⚖️ **Skill Weighting** — Weight in-demand skills (e.g. Spark, dbt) higher than common ones
- 🌐 **Multi-role Support** — Extend to Data Scientist, ML Engineer, Analytics Engineer roles
- ☁️ **Cloud Deployment** — Deploy to Streamlit Community Cloud for public access
- 📊 **Skill Gap Dashboard** — Visual charts showing which skills you're missing most across all jobs

---

## 👨‍💻 Author

<div align="center">

**Abdul Musawir**
*AI/ML Engineer & Data Scientist*
📍 Lahore, Pakistan
🎯 Focus: Data Engineering · Machine Learning · End-to-End ML Apps

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/abdul-musawir-a9713a20b/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Musawir456)
[![Kaggle](https://img.shields.io/badge/Kaggle-Profile-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/abmusawir)

</div>

---

<div align="center">

⭐ **Found this useful? Give it a star!** ⭐

*Made with ❤️ by Abdul Musawir — Lahore, Pakistan*

</div>
