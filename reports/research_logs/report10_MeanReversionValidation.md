
# Day 11: Mean Reversion & Regime Validation Setup

## Project Work

- [x] Defined midpoint-based range structure using upper/lower bounds from rolling windows
- [x] Clarified the two core parameters of Mean Reversion v1: `L` (range window) and `h` (forward horizon)
- [x] Constructed midpoint-based reference columns including `md` and `md3`
- [x] Developed **Mean Reversion v1 (MR)** using current vs future distance-to-midpoint comparison
- [x] Created supporting columns for validation: `dist`, `dist_next`, `mr`, `md`, `md3`, `3m`
- [x] Explored visual comparison methods between price, MR events, and regime labels
- [x] Colored MR points by `regime` to visually inspect whether reversion events cluster in range conditions
- [x] Designed an MD3 reference-line visualization using a linear connection between the first and last quarterly midpoint values
- [x] Solved price-flattening issues in joint plots by separating visual scales appropriately
## Review

- [x] Reviewed the intuition of midpoint as the simplest center of a range
- [x] Rechecked the exact role of `L` in defining the historical structure of the range
- [x] Rechecked the exact role of `h` in measuring whether price returns toward the center
- [x] Confirmed that Mean Reversion v1 uses only distance-to-center and does **not** use point dispersion directly
- [x] Evaluated whether the simple MR definition is sufficient as a baseline validation metric
---
## 📚 What I Learned

- Mean Reversion in its simplest form asks one clear question:  
  **does price move closer to the midpoint after some future horizon, or not?**

- The parameter `L` defines **how much past data is used to estimate the current range structure**.

- The parameter `h` defines **how long we wait before checking whether price reverted**.

- These two parameters are the minimum required ingredients for a simple and interpretable mean reversion framework:
  - a center reference
  - a future check window

- In the baseline version, Mean Reversion does **not** depend on variance or point dispersion; it only compares absolute distance from the midpoint before and after the forward horizon.

- Midpoint is a strong first reference because it is transparent, stable, and easy to interpret in a range-detection context.
---
## 💡 Key Concepts

- **Midpoint**
  The simplest center of a range:
```python
  md = (upper + lower) / 2
  
````

- **Range Window (`L`):** The lookback length used to define the range structure and midpoint.

- **Forward Horizon (`h`):** The number of candles ahead used to check whether price reverted.

- **Event Overlay Visualization:**  MR events are plotted directly on the price chart to visually inspect where mean reversion occurs and under which regime.

---
## 🐛 Problems & Solutions

- **Problem 1:** The exact role of `L` and `h` was conceptually unclear.
- **Solution:** Reframed both parameters in simple intuitive terms:
    - `L` = how much past we use to find the center
    - `h` = how long we wait to see if price comes back

- **Problem 2:** There was uncertainty about whether simple Mean Reversion uses dispersion.
- **Solution:** Clarified that the baseline version uses only **distance to midpoint**, not variance, z-score, or point spread.
- **Problem 3:** Plotting MD3 together with price on one axis caused the price series to appear visually flat.
- **Solution:** Separated scales appropriately and treated MD3 as a background reference rather than forcing both onto one distorted scale.
---

## 🎯 Tomorrow’s Focus

- Continue refining the validation workflow 