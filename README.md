# Smart Aid Finder
### A Data-Driven Aid Matching System | Python · Pandas · SciPy · Matplotlib

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## Project Overview

Smart Aid Finder is a Python-based system that connects people who need help with those who can offer it. Built as a Probability & Statistics project at Riara University, it evolved from a pure software engineering exercise into a full data science pipeline — demonstrating matching algorithms, statistical analysis, and data-driven decision making.

The system matches **300 donors** with **400 receivers** across 5 Kenyan cities, achieving a **71.5% match rate** and identifying statistically significant supply-demand gaps (χ² p = 0.0009).

---

## Repository Structure

```
smart-aid-finder/
│
├── SmartAidFinder.ipynb   # Version 1 — Core system (OOP + matching algorithm)
├── Smart aid finder Improvment.ipynb   # Version 2 — Full data science pipeline
├── donations.csv               # Generated dataset — 300 donation records
├── requests.csv                # Generated dataset — 400 aid request records
└── README.md
```

### Version History
| Version | Focus | Key Addition |
|---|---|---|
| v1 | Software Engineering | OOP classes, matching algorithm, LIFO stack, CSV/JSON export |
| v2 | Data Science | Statistical analysis, hypothesis testing, probability, unmatched deep dive |

---

## System Features

### Core System (v1)
- **UserRegistry** — dictionary-based user management with input validation
- **AidSystem** — donation and request management with urgency sorting
- **Matching Algorithm** — O(R×D) priority matching by category + location
- **MatchHistory** — LIFO stack with undo functionality
- **Export** — JSON and CSV output for persistence and auditing

### Data Science Layer (v2)
- Realistic dataset (300 donations, 400 requests) using Kenya-informed distributions
- Descriptive statistics — mean, median, std, skewness, kurtosis, IQR
- Probability analysis — joint, conditional, and independence testing
- Chi-square hypothesis test — supply vs demand category distributions
- Pearson correlation — location vs urgency relationship
- Unmatched request analysis — failure rates by category and location
- 7 matplotlib visualisations

---

## Key Results

| Metric | Value |
|---|---|
| Total donations | 300 |
| Total requests | 400 |
| Match rate | 71.5% |
| Unmatched requests | 114 (28.5%) |
| Mean urgency score | 2.495 / 5 |
| Urgency skewness | +0.546 (right-skewed — many urgent cases) |
| Chi-square p-value | 0.0009 (supply ≠ demand, statistically significant) |
| Critical requests unmatched | 1.1% |

---

## Dataset

The dataset is **synthetically generated** using real-world distributions informed by:

- [FAOSTAT Kenya Food Security Indicators](https://data.humdata.org/dataset/faostat-food-security-indicators-for-kenya) — category demand weights
- [HDX Kenya Humanitarian Data](https://data.humdata.org/group/ken) — location-level demand patterns

**Distribution decisions:**
- Food (38%) and Medical (25%) dominate requests — consistent with Kenya aid reports
- Nairobi (35%) has the highest demand by population weight
- Urgency follows a right-skewed distribution — most requests are high urgency (levels 1–2)
- Intentional supply gap: 300 donations vs 400 requests reflects real under-supply conditions

---

## Statistical Findings

**Chi-Square Test Result:**
> H₀: Donation and request category distributions are the same  
> Result: REJECT H₀ (p = 0.0009, α = 0.05)  
> Interpretation: The mismatch between what donors give and what receivers need is **statistically significant** — not random. This is the structural cause of the 28.5% unmatched rate.

**Unmatched Analysis:**
- Clothing and Education have the highest failure rates
- Eldoret has the highest location-level unmatched rate
- Even Critical urgency (level 1) requests go unmatched in some categories

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.10 | Core language |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical operations and random generation |
| Matplotlib | Data visualisation (7 charts) |
| SciPy | Chi-square test, Pearson correlation |
| JSON / CSV | Data export and persistence |
| Jupyter Notebook | Development environment |

---

## How to Run

**1. Clone the repository**
```bash
git clone https://github.com/Quinkeizy-dev/smart-aid-finder.git
cd smart-aid-finder
```

**2. Install dependencies**
```bash
pip install pandas numpy matplotlib scipy
```

**3. Open in Jupyter**
```bash
jupyter notebook
```

**4. Run either notebook**
- Start with `SmarAidFinder.ipynb` for the core system
- Open `Smart aid finder improment.ipynb` for the full analysis
- Click **Run All** — `donations.csv` and `requests.csv` will be generated automatically

---

## Future Improvements

- Web interface using Flask or Streamlit
- Demand forecasting using time-series analysis
- Integration with M-Pesa for monetary donations
- Geospatial mapping of supply-demand gaps across Kenyan counties
- Recommendation engine suggesting donation categories based on real-time gaps
- Real user data collection via a mobile form

---

## Author

**Keziah Ndanu Masai**  
BSc Computer Science — Riara University, Nairobi  
[LinkedIn]www.linkedin.com/in/keziah-masai


---

*Built as a Probability & Statistics course project — evolved into a full data science pipeline.*
