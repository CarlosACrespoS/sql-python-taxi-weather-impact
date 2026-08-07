🚕 Chicago Urban Mobility Strategy: Zuber Market-Entry Analysis


![Python](https://img.shields.io/badge/Python-3.12-blue) ![SQL](https://img.shields.io/badge/SQL-Data%20Extraction-4479A1) ![SciPy](https://img.shields.io/badge/SciPy-Statistical%20Inference-8CAAE6) ![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0)

A competitive-intelligence and statistical-validation pipeline supporting Zuber's ride-share launch in Chicago — combining SQL-extracted market, geographic, and weather data with formal hypothesis testing to answer three market-entry questions with numbers, not assumptions.

## 📌 Executive Summary & Strategic Wrap-Up

### 📝 Executive Overview
This project audits Chicago's ride-hailing competitive landscape, maps geographic demand concentration, and statistically validates whether weather disrupts trip times on Zuber's highest-value corridor (Loop → O'Hare). Every finding below is backed by an executed statistical test or a verified aggregate from the underlying SQL-extracted data — not an assumption carried over from the business brief.

### ⚡ Analysis Phase-by-Phase Flashback
- **Phase 1 (Data Sanitization & Temporal Alignment):** Loaded and profiled 3 SQL-extracted sources (company volume, drop-off geography, weather/duration logs), confirmed zero nulls, converted `start_ts` to `datetime`.
- **Phase 2 (Market Structure & Competitive Intelligence):** Built a reusable executive bar-chart function and identified Flash Cab as the dominant incumbent, with **19,558 trips** — nearly double its closest competitor.
- **Phase 3 (Geographic Demand Profiling):** Mapped the top 10 drop-off hotspots; **Loop (10,727 trips)** and **River North (9,524 trips)** lead by a wide margin.
- **Phase 4 (Behavioral Storytelling & Visual Analytics):** A two-panel hero chart visualized the weather-driven trip-duration gap before it was formally tested.
- **Phase 5 (Hypothesis Testing & Statistical Validation):** Levene's test (P = 0.5332, homogeneous variances) + independent t-test (P ≈ 0.0000) confirmed the weather effect is real, not sampling noise.
- **Phase 6 (Executive Conclusions & Business Impact):** Translated every validated finding into fleet, pricing, and ETA recommendations for Zuber's launch.

### 💡 Key Insights & Business Value
- **The incumbent market is concentrated, not impenetrable:** Flash Cab's near-2x lead over its closest competitor, followed by a long tail of smaller players, points to a mature-but-exploitable market rather than one Zuber needs to out-scale on day one.
- **Fleet strategy is a 5-neighborhood problem, not a citywide one:** Loop, River North, Streeterville, West Loop, and O'Hare account for the bulk of drop-off demand — zonation, not blanket coverage, is the efficient launch strategy.
- **Weather friction is quantified, not assumed:** adverse weather adds a validated **21.4%** to average trip duration on Saturdays (33.3 min clear vs. 40.5 min adverse, P ≈ 0.0000, n = 1,068) — a specific number an ETA or pricing algorithm can actually use.

### 🚀 Proactive Recommendations & Strategic Action Plan

| 🚗 Fleet & Launch | 💵 Pricing & ETA | 📊 Ongoing Validation |
|---|---|---|
| Concentrate initial fleet density in the top-5 drop-off hotspots (Loop, River North, Streeterville, West Loop, O'Hare). | Build a weather-adjusted ETA rule using the validated +21.4% duration effect as a starting coefficient. | Extend the hypothesis test beyond Saturdays and beyond Loop → O'Hare to confirm the weather effect generalizes. |
| Compete on service-quality differentiation in zones where incumbents like Flash Cab already dominate volume. | Consider a modest adverse-weather surcharge to incentivize driver supply during storms. | Recalibrate the weather coefficient with real Zuber trip data once the service is live. |

### 📊 Target Business KPIs & Expected Impact

| Strategic Initiative | Primary Target KPI | Statistical Basis |
|---|---|---|
| Top-5 Hotspot Fleet Zonation | Pickup time / vehicle occupancy rate | Loop + River North + Streeterville + West Loop + O'Hare together lead the 94-neighborhood drop-off ranking |
| Weather-Adjusted ETA & Pricing | ETA accuracy during adverse weather | +21.4% average duration under adverse weather, P ≈ 0.0000 (Levene P = 0.5332) |
| Competitive Service Differentiation | Share capture vs. Flash Cab / Taxi Affiliation Services | Top-4 incumbents already concentrate the bulk of the 64-company market's volume |

### 🗂 Project Repository Details
- **Repository Slug:** `sql-python-taxi-weather-impact`
- **Primary Goal:** Equip Zuber's Chicago market-entry strategy with a validated view of competitive structure, demand geography, and weather's real impact on trip duration.
- **Key Achievements:**
  - **Competitive & Geographic Auditing:** Ranked a 64-company market and a 94-neighborhood demand map from SQL-extracted data using a single reusable visualization function.
  - **Statistically Validated Weather Effect:** Confirmed, via Levene's test + independent t-test at 95% confidence, that adverse weather adds 21.4% to average trip duration on the Loop → O'Hare corridor.
  - **Actionable Effect Size, Not Just Significance:** Every hypothesis-test result is reported with its actual magnitude (minutes, percentage) alongside its p-value, so findings translate directly into pricing/ETA logic.

## 💻 Tech Stack & Environment Settings
- **Language:** Python 3.12
- **Data Source:** SQL extraction (Chicago public taxi trip records)
- **Data Processing:** pandas, numpy
- **Statistical Inference:** scipy.stats (Levene's test, independent t-test)
- **Data Visualization:** matplotlib, seaborn
- **Environment:** Jupyter Notebook

## 📁 Repository Structure
```
sql-python-taxi-weather-impact/
├── sql-python-taxi-weather-impact.ipynb      # Full analysis pipeline (executed, outputs included)
├── moved_project_sql_result_01.csv            # Company trip volume (SQL extract)
├── moved_project_sql_result_04.csv            # Drop-off neighborhood averages (SQL extract)
├── moved_project_sql_result_07.csv            # Weather / trip-duration logs (SQL extract)
├── requirements.txt                            # Reproducible environment dependencies
├── README.md
└── .gitignore                                   # Excludes venv/ and generated chart images
```

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/CarlosACrespoS/sql-python-taxi-weather-impact

# Navigate to the project directory
cd sql-python-taxi-weather-impact

# Create and activate a virtual environment (recommended)
python -m venv venv_taxi
source venv_taxi/bin/activate   # Windows: venv_taxi\Scripts\activate

# Install required dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook sql-python-taxi-weather-impact.ipynb
```
