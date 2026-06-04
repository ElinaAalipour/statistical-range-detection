# Day 06 — Candle Range Compression

### Project Work

- [x] Designed Candle Range Compression feature
- [x] Defined candle_range = high - low
- [x] Built rolling baselines (16, 48)
- [x] Created range_rel_16
- [x] Created range_rel_48
- [x] Performed statistical validation
- [x] Performed visual validation
- [x] Saved feature-enhanced dataset (v3)

### Review

- [x] Reviewed volatility compression concepts
- [x] Compared ATR and Candle Range behavior
- [x] Evaluated feature responsiveness
- [x] Investigated extreme values
______
## 📚 What I Learned

- Candle size provides information different from ATR.
- Relative features are more informative than absolute values.
- Compression can be observed directly through candle contraction.
- Multiple feature perspectives improve market-state estimation.
_______
## 💡 Key Concepts

- **Candle Range:** Difference between high and low of a candle.
- **Compression:** Current candle size becomes smaller than its historical average.
- **Relative Feature:** Current measurement divided by historical baseline.

- **Feature Complementarity:** Different features can describe different aspects of the same market condition.
______
## 🐛 Problems & Solutions

- **Problem1:** Needed a feature that directly measures candle-size contraction.
- **Solution:** Constructed relative candle range features using rolling baselines.

- **Problem2:** Large candles produced extreme values.
- **Solution:** Accepted as valid behavior because the feature should react strongly to unusual market activity.

- **Problem3:** Needed evidence that the feature identifies ranging periods.
- **Solution:** Performed visual validation against historical price action.
____
## 🎯 Tomorrow's Focus

- Design Bollinger Band Width feature
- Complete Feature Set v1
- Compare relationships between all features