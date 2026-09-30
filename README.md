# Employee Wellness Analysis 🧠

**Exploratory Data Analysis of workplace mental-health survey data — built for XYZ Technical Solutions to identify employees who may need support and to design targeted wellness programs.**

[![Python](https://img.shields.io/badge/Python-3.10-blue)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/pandas-EDA-150458)](https://pandas.pydata.org/)
[![License](https://img.shields.io/badge/license-MIT-green)](#license)

---

## 📌 Project Overview

XYZ Technical Solutions lost a valued employee to a health crisis and wants to proactively identify employees who are in need of — or may need — mental health support. This project performs a full exploratory data analysis (EDA) on a workplace mental-health survey to uncover which factors (benefits awareness, family history, work interference, company size, etc.) are associated with employees seeking treatment, so HR can design evidence-based wellness programs instead of guessing.

**Key question:** *Which employees are likely to need mental-health support, and what workplace factors predict it?*

---

## 🗂️ Repository Contents

| File | Description |
|---|---|
| `Employee_Wellness_Analysis.pptx` | Slide deck for presenting findings — dataset overview, step-by-step data cleaning (with code), 8 EDA visualizations (each paired with its Python code), key insights, and recommendations |
| `Employee_Wellness_EDA.ipynb` | Jupyter notebook with the full analysis — cleaning, EDA, and insights in one runnable file |
| `employee_wellness_dataset.csv` | Source survey data (1,048 responses × 28 attributes) |

> If any of these files aren't in your local copy of this repo yet, generate the notebook output by running the `.ipynb` end to end — see [Getting Started](#-getting-started) below.

---

## 📊 Dataset

A workplace mental-health survey capturing demographics, workplace stressors, employer support programs, and treatment-seeking behavior.

- **Size:** 1,048 responses, 28 raw attributes
- **Attribute groups:**
  - **Demographics** — Age, Gender, Country, State
  - **Workplace factors** — company size, remote work, tech company, self-employed
  - **Employer support** — benefits, care options, wellness programs, anonymity, leave policy
  - **Attitudes & outcomes** — willingness to disclose, work interference, treatment (target variable)

---

## 🧹 Data Preprocessing

Raw survey data required deliberate cleaning before any chart could be trusted:

1. **Initial inspection** — shape, dtypes, missing values, duplicate rows
2. **Age outliers** — impossible values (`-1726`, `99999999999`) replaced with `NaN`; valid range kept to 18–75
3. **Gender standardization** — 37 free-text spellings (`'Male-ish'`, `'Cis Female'`, `'malr'`...) collapsed into 3 clean categories via a lookup function
4. **Corrupted category labels** — Excel auto-date corruption (`'25-Jun'` → `'6-25'`, `'5-Jan'` → `'1-5'`) repaired and reordered as an ordered categorical
5. **Missing values & column pruning** — `self_employed` mode-imputed, `work_interfere` blanks labeled `'Not Applicable'` (the condition didn't apply, not truly missing), `comments` (87% missing) dropped

Every step is documented with its exact pandas code in both the notebook and the presentation.

---

## 🔍 Exploratory Analysis

Eight visualizations, each paired with the Python code that generated it:

1. Age distribution
2. Gender distribution
3. Treatment-seeking overall
4. Family history vs. treatment
5. Work interference vs. treatment
6. Company size vs. treatment
7. Benefits awareness vs. treatment
8. Respondent geography

---

## 💡 Key Insights

- **Family history is the strongest predictor** — employees with a family history of mental illness seek treatment at **57.8%**, nearly 3× the rate of those without (**20.3%**)
- **Self-reported work interference tracks closely with treatment-seeking** — a practical, low-friction check-in cue for managers
- **Awareness of benefits drives usage more than the benefits' existence alone** — 62% treatment rate among employees who know benefits exist, vs. 36% among those who say "don't know"
- **Nearly half of all respondents (48.9%) have already sought treatment** — this is a mainstream workplace issue, not a fringe one
- **Company size and remote-work status show only mild effects** — culture and communication matter more than structure
- The sample skews young, male, and US/UK-based — findings should be validated against XYZ's actual workforce before rollout

---

## ✅ Recommendations for XYZ

1. **Communicate benefits clearly** — awareness alone raised treatment-seeking by up to 26 points
2. **Train managers to recognize warning signs** — self-reported work interference is a strong, actionable cue
3. **Build in proactive check-ins** — don't rely on opt-in programs alone, given ~49% already need support
4. **Protect anonymity** — willingness to disclose to supervisors/coworkers varies widely; offer confidential channels
5. **Validate on XYZ's own data** — re-run this analysis on XYZ's employee survey before finalizing any program

---

## 🚀 Getting Started

```bash
# Clone the repo
git clone https://github.com/<your-username>/employee-wellness-analysis.git
cd employee-wellness-analysis

# Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# Run the notebook
jupyter notebook Employee_Wellness_EDA.ipynb
```

To view the presentation, open `Employee_Wellness_Analysis.pptx` in PowerPoint, Keynote, or Google Slides.

---

## 🛠️ Tools Used

- **Python** — pandas, NumPy for data wrangling
- **Matplotlib / Seaborn** — visualizations
- **Jupyter Notebook** — analysis environment

---

## 📄 License

This project is released under the [MIT License](LICENSE). The dataset is derived from a public workplace mental-health survey (OSMI) and is used here for educational purposes only.

---

## 🙋 About

Built as an Exploratory Data Analysis (EDA) project applying data cleaning, visualization, and insight generation to a real-world workplace wellness dataset.
