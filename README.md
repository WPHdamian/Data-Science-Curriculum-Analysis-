# Aligning Data Science Education with Labour Market Needs
---

## Project Overview

This repository supports the final-year research project for BSSc in Data Science and Policy Studies:

> **“Aligning Data Science Education with Labour Market Needs: A Comparative Analysis of Programme Design and Skill Demand in Hong Kong and London.”**

The study investigates how well Data Science programmes in two global higher-education hubs-**Hong Kong** and **London**—align with skill requirements in the data-driven labour market.

This repository contained the first part of this research. With Natural Language Processing (NLP) and topic modelling, the research aims to compare curricula across universities and map academic emphasis against employer-demanded competencies.

---

## Repository Structure

```
├── data/
│   ├── curriculum_dataset.csv
│   ├── job_market_data.csv (planned)
│
├── notebooks/
│   ├── curriculum_analysis_FYP.ipynb
│   ├── jobmarket_analysis_FYP.ipynb (planned)
│
└── README.md
```

---

## Dataset Description

### `curriculum_dataset.csv`

| Column               | Description                                                    |
| -------------------- | -------------------------------------------------------------- |
| `city`               | City where the university is located (`Hong Kong` or `London`) |
| `university`         | Name of the institution                                        |
| `program_name`       | Full title of the Data Science-related programme               |
| `faculty`            | Faculty or department offering the programme                   |
| `level`              | Undergraduate or postgraduate                                  |
| `module_code`        | Course/module code (if available)                              |
| `module_title`       | Official title of the module                                   |
| `module_description` | Text description of course objectives and content              |
| `core_or_elective`   | Whether the module is compulsory or elective                   |

> Only programmes containing **“Data Science,” “Data Analytics,” “Big Data,” “Business Analytics,” or “Data Engineering”** in their title were included.

---

## Analytical Workflow

| Step                                             | Description                                                                                                              | Key Tools                           |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ----------------------------------- |
| **1. Data Cleaning**                             | Standardised and deduplicated raw programme data. Added identifiers for shared modules.                                  | `pandas`, `numpy`                   |
| **2. Text Preprocessing**                        | Tokenisation, lemmatisation, and stopword removal applied to module text.                                                | `spaCy`, `nltk`                     |
| **3. Frequency Analysis**                        | Extracted high-frequency words to identify common curricular themes.                                                     | `collections.Counter`, `matplotlib` |
| **4. Skill Mapping**                             | Mapped curricular terms to skill categories based on **LinkedIn Skills Taxonomy (2023)** and **OECD (2020)** frameworks. | Custom dictionary mapping           |
| **5. Topic Modelling (LDA)**                     | Uncovered latent topics within curricula using **Latent Dirichlet Allocation** to identify thematic clusters.            | `gensim`, `pyLDAvis`                |
| **6. Comparative Analysis**                      | Compared topic prevalence and skill emphasis between cities.                                                             | `pandas`, `seaborn`                 |
| **7. (Planned)** Curriculum–Job-Market Alignment | Match curricula with job-posting skill data to identify alignment gaps.                                                  | `TF–IDF`, `cosine_similarity`       |

---

## Preliminary Findings

* Both Hong Kong and London curricula are **technically focused**, dominated by programming and statistical modelling content.
* **London programmes** integrate more **policy and socio-economic themes**, while **Hong Kong programmes** emphasise **business analytics and applied decision-making**.
* Thematic analysis revealed **five major curriculum topics**, with a coherence score (C-V value) of **0.282**, indicating meaningful differentiation despite text brevity.
* Early evidence suggests **skill misalignment**, particularly in transversal skills (communication, teamwork, project management).

---

## Dependencies

Install dependencies with:

```bash
pip install pandas numpy matplotlib seaborn spacy gensim pyLDAvis nltk scikit-learn
python -m spacy download en_core_web_sm
```

---

## Reproducibility

1. Clone the repository:

   ```bash
   git clone https://github.com/[yourusername]/data-science-education-alignment.git
   cd data-science-education-alignment
   ```
2. Open Jupyter Notebook:

   ```bash
   jupyter notebook
   ```
3. Run notebooks sequentially inside `notebooks/`.
4. Outputs (plots, CSVs, topic summaries) will appear in the `outputs/` folder.
5. 
---

## References

* LinkedIn Economic Graph. (2023). *LinkedIn Skills Taxonomy: Mapping Global Skills.*
* OECD. (2020). *Skills Outlook 2020: Thriving in a Digital World.* OECD Publishing.
* World Economic Forum. (2023). *Future of Jobs Report 2023.*
* Blei, D. M., Ng, A. Y., & Jordan, M. I. (2003). *Latent Dirichlet Allocation.* *Journal of Machine Learning Research*, 3, 993–1022.
* SpaCy & Gensim Documentation (for NLP pipeline setup).

---
