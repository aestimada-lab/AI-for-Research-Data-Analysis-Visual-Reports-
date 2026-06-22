# AI-for-Research-Data-Analysis-Visual-Reports-
# Automated Visual Data Report  
## Regional Development Analytics Dashboard (Mindanao Focus)

### Dataset Focus: Socio-Economic & Environmental Indicators — Mindanao Regional CSV (Raw Input Simulation)

---

## 1. Data Cleaning Protocol Log (AI Processing Summary)

### Raw Data Issues Identified
- Inconsistent numeric formats (kg, MT, and mixed unit strings in single columns)
- Missing values in key indicators (notably 2022–2024 waste output and crop yield rows)
- Duplicate municipal entries across provincial datasets
- Date formatting inconsistencies (MM/DD/YYYY vs YYYY only)
- Outlier spikes in energy production likely caused by encoding or ingestion errors

### AI Cleaning Operations Executed
- Standardized all mass-based metrics to Metric Tons (MT)
- Imputed missing values using:
  - Median substitution for agricultural yield columns
  - Forward-fill interpolation for energy production time series
- Removed duplicate municipal records (14 duplicates merged)
- Normalized all timestamps to YYYY format
- Flagged extreme outliers (>3σ) for policy-level review (not deleted)

### Cleaned Output Snapshot (Sample Structure)

| Year | Crop Yield (MT) | Energy Production (GWh) | Waste Output (MT) |
|------|-----------------|--------------------------|-------------------|
| 2020 | 182,400         | 3,210                    | 45,120            |
| 2021 | 190,880         | 3,455                    | 47,002            |
| 2022 | 175,210         | 3,390                    | 52,610            |
| 2023 | 149,005         | 3,120                    | 58,940            |
| 2024 | 161,780         | 3,610                    | 60,115            |

---

## 2. Visualizations Generated

### Chart 1: Agricultural Yield vs Environmental Stress Indicators (2020–2024)

```mermaid
xychart-beta
    title "Mindanao Crop Yield vs Waste Output Trends"
    x-axis [2020, 2021, 2022, 2023, 2024]
    y-axis "Metric Units (Normalized Index)" 0 --> 200000
    line "Crop Yield (MT)" [182400, 190880, 175210, 149005, 161780]
    line "Waste Output (MT)" [45120, 47002, 52610, 58940, 60115]
