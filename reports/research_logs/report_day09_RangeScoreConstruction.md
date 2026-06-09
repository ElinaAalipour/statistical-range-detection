# Day 9: Range Score Construction & Regime Visualization

## Project Work

- [x] Normalized selected features using percentile rank transformation
- [x] Created inverted compression scores using 1−percentile rank 1 - \text{percentile rank} 1−percentile rank
- [x] Generated standardized feature set (`*_s`) excluding non‑feature columns (e.g., close)
- [x] Constructed **Range Score v1 (0–100)** using equal‑weighted aggregation
- [x] Implemented discrete regime labeling (-1, 0, 1) based on score thresholds
- [x] Designed event‑based visualization for regime validation
- [x] Built continuous regime shading chart for structural interpretation
- [x] Refined visualization logic to avoid marker overlap and improve interpretability

## Review

- [x] Reviewed statistical interpretation of percentile normalization
- [x] Evaluated equal‑weight aggregation vs weighted alternatives
- [x] Validated threshold logic (0–40, 40–60, 60–100) for regime separation
- [x] Assessed visual alignment between high score regions and range‑like price behavior
- [x] Compared event‑based vs continuous regime visualization approaches

---
## 📚 What I Learned

- Percentile normalization transforms heterogeneous volatility features into a **comparable probabilistic scale**.
- Inverting the percentile rank effectively converts volatility measures into **compression intensity signals**.
- Equal‑weighted aggregation provides a transparent and explainable baseline model.
- Regime detection benefits from separating **continuous signal strength (score)** from **discrete trading state (regime)**.
- Visualization design critically affects interpretability; marker overlap can distort perception of model behavior.

---
### 💡 Key Concepts

- **Percentile Rank Normalization:**
  Transforms heterogeneous volatility features into a comparable probabilistic scale between 0 and 1.
```python
s_i = 1 - rank_pct(x_i)
```

Where:
- `x_i` = original feature value
- `rank_pct()` = percentile rank within the full sample
- `s_i` = compression score

- **Range Score (v1):**
  Aggregates normalized compression signals into a single interpretable metric.
```python
RangeScore = mean([atr_rel_16_s, std_rel_48_s, range_rel_48_s]) * 100
```
Properties:
- Range: **0 – 100**
- Higher score → stronger volatility compression
- Lower score → higher volatility expansion

- **Equal‑Weighted Aggregation:**
  A transparent baseline ensemble method where each feature contributes equally to the final score.
Advantages:
- Fully interpretable
- No parameter optimization required
- Serves as a stable benchmark for future model versions

- **Regime Labeling:**
  The continuous score is converted into discrete market regimes.
```python
Regime =
-1   if RangeScore < 40
 0   if 40 ≤ RangeScore < 60
 1   if RangeScore ≥ 60
```
Interpretation:
- **-1 → Trend / Expansion**
-  **0 → Transitional / Neutral**
-  **1 → Range / Compression**

- **Event Overlay Visualization:**
  High-confidence signals are plotted slightly above the price series to avoid marker overlap and improve visual interpretability when validating regime behavior.

---
## 🐛 Problems & Solutions

- **Problem 1:** Feature scaling differences prevented direct aggregation.
- **Solution:** Applied percentile rank normalization to ensure comparability.

- **Problem 2:** Inclusion of non‑feature columns (e.g., close) in scaling loop created unintended derived columns.
- **Solution:** Explicitly filtered feature list to exclude
  price columns before normalization.

- **Problem 3:** Severe marker overlap between `regime=1` and `score>60` events reduced visualization clarity.

- **Solution:**

    - Used different marker shapes
    - Applied hollow markers
    - Offset high‑score markers vertically using adaptive price standard deviation

- **Problem 4:** Continuous regime shading initially obscured price structure.
- **Solution:** Reduced alpha levels and clarified legend positioning for improved readability.

---
## 🎯 Tomorrow’s Focus

- Perform **statistical validation of the Range Detection Engine** to evaluate whether detected regimes correspond to distinct market behaviors.