# Competing for Clean Air: Dynamic Incentives in China's Environmental Protection Interviews

**Status:** Job Market Paper (2026)
**Keywords:** Difference-in-Differences, Staggered Treatment, Tournament Theory, Air Pollution, Health Economics, China

---

## Research Question

China's Environmental Protection Interview (EPI) policy ranks cities by air quality
and publicly targets the worst performers. I ask: does ranking-based competitive
pressure actually reduce pollution — and if so, who responds, when, and why?

Prior literature focused on cities that were formally sanctioned and found modest
effects (~4 μg/m³). This paper reframes the question around *competitive risk*:
cities that are at risk of being ranked at the bottom, not just those already
penalized.

---

## Key Findings

- Cities at risk of EPI sanctions reduced PM2.5 by **12.6 μg/m³** on average —
  roughly 3× larger than prior estimates
- Reductions are **seasonal**, peaking at 21.7 μg/m³ in December around evaluation
  windows and weakening mid-year — consistent with short-term strategic abatement
- **Political connections** intensify short-term reductions near evaluation windows;
  **capital proximity** produces steadier year-round improvements
- A **tournament model** separates these two patterns by distinguishing rank-loss
  costs from pollution damage costs
- The policy generates measurable **healthcare cost savings** during evaluation
  periods, though patient volumes show no significant change

---

## Data

| Source | Description |
|---|---|
| TAP satellite PM2.5 | Daily, 1 km resolution, 2000–present |
| Government health records | Self-collected from ~hundreds of PNG files on provincial websites; manually reconstructed into panel |
| EPI announcement dates | Chinese Ministry of Ecology and Environment |
| Political network data | Provincial leadership connections, self-collected and matched |
| City-level controls | GDP, industrial share, population |

*Raw data cannot be shared due to data agreements and collection constraints.*

---

## Methods

- **Callaway–Sant'Anna DiD** with staggered treatment timing — avoids the negative
  weighting problem in two-way fixed effects with heterogeneous treatment
- **Continuous treatment specification** to capture intensity of EPI risk exposure
- **Tournament model** (structural) to separate political and geographic mechanisms
- Robustness: event study plots, spatial spillover checks, alternative comparison
  groups, matching-based approaches

---

## Code Sample

`Code_sample/` contains examples of:
- Data cleaning pipeline for high-frequency satellite PM2.5 data
- Panel construction from fragmented administrative sources
- DiD estimation with `csdid` / Callaway–Sant'Anna implementation

---

## Connection to Health Research

The healthcare cost savings analysis in this paper uses a similar logic to
pharmacoeconomic evaluation: mapping a policy-induced change in an exposure
(PM2.5) to avoided health events and their associated costs. The main limitation
is that the Chinese data does not allow patient-level clinical linkage. Richer
longitudinal clinical data (e.g., EHR-linked records) would allow more precise
welfare estimation — a direction I am actively interested in extending.

---

## Author

Mengshan Zhao | mengshan.zhao@wsu.edu | [www.mengshanzhao.com](https://www.mengshanzhao.com)
