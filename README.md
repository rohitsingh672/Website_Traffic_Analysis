# 🎵 Alfido Tech — Website Traffic Analysis

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-150458?style=flat&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7+-11557c?style=flat)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat&logo=jupyter&logoColor=white)
![ReportLab](https://img.shields.io/badge/ReportLab-PDF-red?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-10b981?style=flat)

> End-to-end analysis of 226,278 music platform traffic events to uncover user journeys, top content, geographic performance, and actionable conversion optimizations.

---

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Dataset](#-dataset)
- [Key Findings](#-key-findings)
- [Project Structure](#-project-structure)
- [Deliverables](#-deliverables)
- [Tech Stack](#-tech-stack)
- [Setup & Usage](#-setup--usage)
- [5 Recommendations](#-5-recommendations)
- [Author](#-author)

---

## 🔍 Project Overview

This project analyzes website traffic logs for **Alfido Tech**, a music streaming/discovery platform. The goal is to understand how users navigate the site, which content drives engagement, where users drop off, and how to improve the overall conversion funnel.

**Business Questions Answered:**
- What is the bounce rate and how can it be reduced?
- Which tracks and artists drive the most traffic and conversions?
- Which geographic markets are underperforming relative to their traffic volume?
- What does a typical user journey look like?
- What are the top 5 actions to improve conversion rates?

---

## 📦 Dataset

| Property | Value |
|---|---|
| **File** | `traffic.csv` |
| **Total Events** | 226,278 |
| **Date Range** | Aug 19 – 25, 2021 (7 days) |
| **Unique Sessions** | 3,839 (by `linkid`) |
| **Unique Tracks** | 3,562 |
| **Countries** | 100+ |

### Columns

| Column | Description |
|---|---|
| `event` | Event type: `pageview`, `click`, or `preview` |
| `date` | Date of event (YYYY-MM-DD) |
| `country` | User's country |
| `city` | User's city |
| `artist` | Artist name |
| `album` | Album name |
| `track` | Track name |
| `isrc` | International Standard Recording Code |
| `linkid` | Unique session/link identifier (used to reconstruct journeys) |

---

## 📊 Key Findings

### Traffic Overview

| Metric | Value |
|---|---|
| Total Page Views | 142,015 |
| Total Clicks | 55,732 |
| Total Previews | 28,531 |
| Unique Sessions | 3,839 |
| **Bounce Rate** | **40.5%** |
| Click-Through Rate | 39.2% |
| Session Engagement Rate | 59.5% |

### User Journey Breakdown

```
Page View Only (Bounce)      ████████████████░░░░░░░░░░░░░░   40.5%  (1,553 sessions)
PV → Preview → Click         ██████████░░░░░░░░░░░░░░░░░░░░   25.7%  (987 sessions)
PV → Click (Direct)          ██████░░░░░░░░░░░░░░░░░░░░░░░░   17.0%  (651 sessions)
PV → Preview (Unconverted)   ██████░░░░░░░░░░░░░░░░░░░░░░░░   16.9%  (648 sessions)
```

### Top 5 Tracks by Pageviews

| Rank | Track | Artist | Pageviews | Clicks | CTR |
|---|---|---|---|---|---|
| 1 | Jalebi Baby | Tesher | 25,175 | 9,692 | 38.5% |
| 2 | Beautiful | Anne-Marie | 6,826 | 2,173 | 31.8% |
| 3 | Beautiful Day | Tundra Beats | 5,982 | 2,198 | 36.7% |
| 4 | ily (i love you baby) | Surf Mesa, Emilee | 4,826 | 1,589 | 32.9% |
| 5 | So Pretty | Reyanna Maria | 3,670 | 1,245 | 33.9% |

### Geographic Performance

| Country | Pageviews | CTR | Note |
|---|---|---|---|
| Saudi Arabia | 28,873 | 32.9% | Largest audience, lowest CTR → localisation gap |
| India | 27,286 | 42.5% | High volume + strong conversion |
| United States | 20,839 | 45.7% | Balanced performance |
| Pakistan | 3,212 | **51.5%** | Highest CTR — most efficient market |
| Turkey | 2,462 | 26.6% | Lowest CTR — needs attention |

---

## 📁 Project Structure

```
alfido-tech-traffic-analysis/
│
├── data/
│   └── traffic.csv                        # Raw traffic log dataset
│
├── notebooks/
│   └── alfido_traffic_analysis.ipynb      # Executed analysis notebook
│
├── outputs/
│   ├── alfido_tech_dashboard.png          # 8-panel analytics dashboard
│   ├── alfido_journey_flow.png            # User journey flow visualization
│   └── alfido_tech_traffic_report.pdf     # Full 5-page PDF report
│
└── README.md
```

---

## 📦 Deliverables

### 1. 📓 Jupyter Notebook
`notebooks/alfido_traffic_analysis.ipynb`

Fully executed notebook with:
- Data loading, cleaning & validation
- Core metric computation (bounce rate, CTR, funnel)
- 8-panel dark-themed analytics dashboard
- User journey flow classification
- Printed insights & recommendations

### 2. 📊 Analytics Dashboard
`outputs/alfido_tech_dashboard.png`

Eight panels in a single dark-themed image:
- Daily event trends (pageview / click / preview)
- Top 10 tracks by pageviews
- Top 10 tracks by clicks
- Engagement funnel (PV → Preview → Click)
- Bounce rate donut chart
- Top 10 countries grouped bar chart
- Top 10 tracks by CTR %

### 3. 🗺️ User Journey Flow
`outputs/alfido_journey_flow.png`

Horizontal flow chart mapping all 3,839 sessions into the four journey archetypes.

### 4. 📄 PDF Report
`outputs/alfido_tech_traffic_report.pdf`

5-page professional report (dark theme) covering:
- Executive summary with KPI table
- Embedded dashboard and journey flow visuals
- Deep-dive tables: top content & geographic performance
- 5 prioritised, evidence-backed recommendations

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, aggregation |
| `numpy` | Numerical operations |
| `matplotlib` | Custom charting (dark theme) |
| `seaborn` | Statistical visualizations |
| `reportlab` | PDF report generation |
| `nbformat` | Notebook creation |
| `nbconvert` | Notebook execution |
| `jupyter` | Interactive analysis environment |

---

## ⚙️ Setup & Usage

### 1. Clone the repository
```bash
git clone https://github.com/your-username/alfido-tech-traffic-analysis.git
cd alfido-tech-traffic-analysis
```

### 2. Create and activate a conda environment
```bash
conda create -n trafficenv python=3.10 -y
conda activate trafficenv
```

### 3. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn reportlab nbformat nbconvert jupyter ipykernel
python -m ipykernel install --user
```

### 4. Place the dataset
```bash
# Put traffic.csv in the data/ folder
cp /path/to/traffic.csv data/
```

### 5. Run the notebook
```bash
jupyter lab notebooks/alfido_traffic_analysis.ipynb
```

### 6. Re-generate the PDF report (optional)
```bash
python scripts/generate_report.py   # if extracted from notebook
```

> **Note:** The notebook reads from `/mnt/user-data/uploads/traffic.csv` by default (Alfido Tech environment). Update the path in Cell 2 if running locally.

---

## 💡 5 Recommendations

| # | Recommendation | Expected Impact |
|---|---|---|
| 1 | **Auto-Preview on page load** — trigger a 3–5 sec audio snippet automatically to reduce the 40.5% bounce rate. Pilot in Saudi Arabia first. | 8–15% bounce reduction |
| 2 | **Localise Saudi Arabia & Turkey pages** — Arabic and Turkish UI/copy to close the CTR gap (32.9% and 26.6% vs 45%+ in US). | 10%+ CTR uplift |
| 3 | **Double down on "Jalebi Baby"** — feature it in homepage hero, emails, and push notifications; build artist crosslink pages for Tesher fans. | Extended virality, higher session depth |
| 4 | **Retarget PV→Preview cohort (648 sessions)** — serve a follow-up email/push within 24 hrs. Converting 30% adds ~190 free clicks. | ~190 incremental conversions at $0 CAC |
| 5 | **A/B test preview-first layout in India & Pakistan** — place audio player above the fold; run for 14 days and roll out globally if CTR lifts >5%. | 5%+ global CTR improvement |

---

## 👤 Author

**Rohit**
Intern — Data Analytics | Alfido Tech
*June 2026*

---

## 📄 License

This project is for internship/educational purposes as part of the Alfido Tech Data Analytics programme.
