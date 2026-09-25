# 🌫️ Air Quality Index (AQI) Analysis — India (April 2022 – April 2025)

**Author:** Akriti Singh  
**Dataset:** `aqi.csv` — Daily city-level AQI readings across Indian states  
**Notebook:** `AkritiSingh_AQIProject.ipynb`  
**Report:** `AkritiSingh_ProjectReport.docx`

---

## 📋 Project Overview

This project performs an end-to-end analysis of real-world Air Quality Index (AQI) data collected from government monitoring stations across India. The dataset spans **April 2022 to April 2025** and contains approximately **235,785 rows**, covering daily readings for hundreds of cities.

**Goals:**
- Clean and pre-process the raw AQI dataset
- Explore AQI distribution, trends, and patterns through EDA
- Create 5 informative charts (+ 1 model chart)
- Build a simple Decision Tree classifier to predict AQI categories

---

## 📁 Project Structure

```
.
├── aqi.csv                          # Raw dataset (source data)
├── AkritiSingh_AQIProject.ipynb     # Main Jupyter notebook
├── AkritiSingh_ProjectReport.docx   # Written project report
├── requirements.txt                 # Python dependencies
└── README.md                        # This file
```

Charts saved by the notebook (auto-generated on run):
```
chart1_aqi_distribution.png     # Pie chart — AQI category distribution
chart2_monthly_trend.png        # Line chart — monthly average AQI trend
chart3_top_states.png           # Horizontal bar — top 10 polluted states
chart4_pollutant_frequency.png  # Bar chart — prominent pollutant counts
chart5_seasonal_pattern.png     # Bar chart — average AQI by month
chart6_feature_importance.png   # Bar chart — Decision Tree feature importance
```

---

## 🚀 Quick Start

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Launch Jupyter

```bash
jupyter notebook AkritiSingh_AQIProject.ipynb
```

### 3. Run all cells

Use **Kernel → Restart & Run All** to execute the full notebook from scratch.

> **Note:** Make sure `aqi.csv` is in the **same directory** as the notebook before running.

---

## 📊 Dataset Columns

| Column | Description |
|---|---|
| `date` | Date of reading (DD-MM-YYYY) |
| `state` | Indian state |
| `area` | City / monitoring area |
| `number_of_monitoring_stations` | Stations aggregated for the city reading |
| `prominent_pollutants` | Comma-separated pollutant codes (PM10, PM2.5, O3, CO, NO2, SO2) |
| `aqi_value` | AQI index value (higher = worse) |
| `air_quality_status` | Category label (Good / Satisfactory / Moderate / Poor / Very Poor / Severe) |

---

## 🔬 AQI Category Reference (CPCB India)

| Category | AQI Range | Health Implication |
|---|---|---|
| Good | 0 – 50 | Minimal impact |
| Satisfactory | 51 – 100 | Minor breathing discomfort for sensitive people |
| Moderate | 101 – 200 | Discomfort for people with lung/heart disease |
| Poor | 201 – 300 | Breathing discomfort on prolonged outdoor exposure |
| Very Poor | 301 – 400 | Respiratory illness on prolonged exposure |
| Severe | 401 – 500 | Health effects in healthy people, serious risk for sensitive groups |

---

## 📈 Charts Produced

1. **AQI Category Distribution** — Proportions of all six AQI categories across the full dataset
2. **Monthly Average AQI Trend** — National average AQI month-by-month from Apr 2022 to Apr 2025
3. **Top 10 Most Polluted States** — Ranked by average AQI over the full period
4. **Prominent Pollutant Frequency** — How often each pollutant is the "prominent" pollutant
5. **Seasonal AQI Pattern** — Average AQI by calendar month (aggregated across all years)

---

## 🤖 Prediction Model

A **Decision Tree Classifier** (max depth = 6) is trained to predict the AQI category using:
- `aqi_value` — the AQI index reading
- `month` — calendar month (1–12)
- `number_of_monitoring_stations` — station count for that city

The model achieves high accuracy, which is expected: AQI categories are directly derived from AQI values using CPCB-defined thresholds. The result confirms the data is internally consistent. Feature importance shows `aqi_value` dominates, as expected.

---

## 💡 Key Findings

- **PM10** is the dominant pollutant across India, driven by dust, construction, and vehicular emissions
- **Winter months (Nov–Jan)** have the highest AQI; **monsoon months (Jul–Sep)** the lowest
- **Rajasthan, Uttar Pradesh, Haryana, and Delhi** are consistently the most polluted states
- **Southern and north-eastern states** (Tamil Nadu, Kerala, Karnataka, Assam) have the cleanest air
- Most Indian cities fall in the **Satisfactory to Moderate** range on an average day

---

## 🛠️ Libraries Used

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, aggregation |
| `numpy` | Numerical operations |
| `matplotlib` | All charts and visualisations |
| `scikit-learn` | Decision Tree model, train/test split, metrics |
| `jupyter` | Interactive notebook environment |

---

## 📄 License

This project is submitted for academic purposes. Dataset sourced from the Central Pollution Control Board (CPCB), India.
