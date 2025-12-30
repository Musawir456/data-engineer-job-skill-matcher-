# Data Engineer Job Skill Matcher

Match your skills to real data engineer job postings scraped from Glassdoor-style listings using Python, pandas and Streamlit.

## 1. Project overview

This project lets you paste your skills and immediately see which real data engineer roles you match best.

- Cleans raw job descriptions and extracts a set of core data engineering skills.
- Compares your skills against each job and calculates a simple overlap score.
- Shows best-matching jobs with matched vs missing skills so you can see gaps.
- Built as an interactive Streamlit app for quick experimentation.

Use‑cases:

- Identify which data engineer jobs fit your current skillset.
- Discover missing tools / technologies to learn next.
- Showcase end‑to‑end data engineering + Python + Streamlit skills in your portfolio. [web:656][web:665]

## 2. Tech stack

- **Language:** Python 3.10
- **Libraries:** pandas, numpy, re, streamlit
- **Environment:** Jupyter Notebook for EDA + feature engineering
- **Version control:** Git & GitHub

## 3. Dataset

- Source: Data engineer job postings CSV (`DataEngineer.csv`).
- Key columns:
  - `Job Title`, `Company Name`, `Location`, `Job Description`
  - `Rating`, `Salary Estimate`, company metadata, etc.
- Engineered columns:
  - `clean_desc`: lower‑cased, punctuation‑stripped job description text.
  - `job_skills`: list of extracted skills present in each job description.

The cleaned dataset used by the app is stored as `data/data_engineer_jobs_clean.csv`.

## 4. Project structure

PROJECT_5/
├── app/
│ ├── matcher.py # Matching logic and scoring
│ └── streamlit_app.py # Streamlit UI
├── data/
│ └── data_engineer_jobs_clean.csv
├── 01_data_engineer_skill_matcher.ipynb # EDA + text cleaning + skill extraction
├── DataEngineer.csv # Raw job postings
└── README.md


## 5. How the matching works

1. **Text cleaning**

   - Convert job descriptions to lowercase.
   - Remove special characters and extra whitespace.
   - Store cleaned text in `clean_desc`.

2. **Skill extraction**

   - Maintain a list of core data engineering skills  
     (e.g. python, sql, spark, aws, airflow, docker, kafka, hadoop, dbt, snowflake, redshift, bigquery, etc.).
   - For each job, check which of these skills appear in `clean_desc`.
   - Save the unique skills found as `job_skills` for that row.

3. **User matching**

   - User enters a comma‑separated list of skills in the Streamlit UI.
   - Convert to a normalized list (lowercase, stripped).
   - For each job:
     - `matched_skills` = intersection(user_skills, job_skills)
     - `missing_skills` = job_skills − user_skills
     - `score` = number of matched skills
   - Sort jobs by `score` (descending) and show top‑K jobs with details. [web:656][web:670]

## 6. How to run locally

1. **Clone the repo**

git clone https://github.com/Musawir456/data-engineer-job-skill-matcher-.git
cd data-engineer-job-skill-matcher-

2. **Create and activate environment** (example using conda)


2. **Create and activate environment** (example using conda)


3. **Start the Streamlit app**


4. Open the browser at `http://localhost:8501` and try different skill combinations.

## 7. Future improvements

- Use NLP libraries (spaCy, keyword extraction, embeddings) for smarter skill detection.
- Weight skills by importance instead of simple counts.
- Support multiple roles (Data Scientist, ML Engineer, Analytics Engineer).
- Deploy the app to Streamlit Community Cloud or another cloud platform. [web:661][web:665]
pandas
numpy
streamlit



## 8. Author

**Abdul Musawir**

- Data & ML enthusiast based in Lahore, Pakistan  
- Focus areas: data engineering, machine learning, end‑to‑end ML apps

**Find me online**

- GitHub: [Musawir456](https://github.com/Musawir456)
- LinkedIn: (https://www.linkedin.com/in/abdul-musawir-a9713a20b/)
- Kaggle: (https://www.kaggle.com/abmusawir)
