# EPI PM2.5 Analysis

**Full Title:** Competing for Clean Air: Dynamic Incentives in China's Environmental Protection Interviews  
**Status:** Working Paper (2025 Job Market Paper)  
**Keywords:** Difference-in-Differences, Tournament Theory, Environmental Policy, PM2.5, China

---

## Project Overview
This project examines the *Environmental Protection Interview* (EPI), a high-profile, ranking-based environmental policy in China.  
Using high-frequency satellite PM2.5 data, I investigate how competitive, ranking-based incentives affect local governments' pollution reduction strategies.

**Key Findings:**
- Cities at risk of EPI sanctions reduced PM2.5 concentrations by **15.7 μg/m³** — ~4x larger than previous estimates.
- Reductions peak in evaluation periods, showing strong **short-term, strategic behavior**.
- Political connections and capital-region oversight shape the *duration* and *consistency* of improvements.

---

## Data
This analysis combines:
- **Satellite-based PM2.5 concentration** (TAP program, 2013–2022, daily)
- **City-level EPI announcement dates** from Chinese Ministry of Ecology and Environment
- **Political network data** (provincial leadership connections)
- **Weather controls** (temperature, precipitation, wind speed)

*Note: Raw datasets cannot be shared. *

---

## Methods
- **Difference-in-Differences (DiD)** with multiple groups & periods  
- **Continuous treatment specification** to capture intensity of EPI risk  
- **Tournament theory** framing for dynamic incentives  
- Seasonal controls to account for heating and weather-driven PM2.5 variation  

---

## Example: Synthetic DiD Implementation
```python
import pandas as pd
import statsmodels.formula.api as smf

# Synthetic panel dataset
df = pd.DataFrame({
    'city': ['A']*4 + ['B']*4,
    'year': [2018, 2019, 2020, 2021]*2,
    'pm25': [60, 55, 50, 48, 65, 64, 58, 56],
    'treat': [0, 0, 1, 1, 0, 0, 0, 0]
})

model = smf.ols("pm25 ~ treat + C(city) + C(year)", data=df).fit(cov_type='cluster', cov_kwds={'groups': df['city']})
print(model.summary())
