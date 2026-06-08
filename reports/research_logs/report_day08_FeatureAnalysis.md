# Day 8: Feature Correlation Analysis & Initial Feature Selection 

### Project Work 

- [x] Computed Pearson correlation matrix for all engineered volatility features
- [x] Computed Spearman correlation matrix to capture monotonic relationships
- [x] Visualized correlation structure using heatmaps
- [x] Examined cross‑feature relationships across volatility indicators (ATR, STD, Candle Range, BB Width)
- [x] Compared correlations across different horizons (16, 48)
- [x] Performed hierarchical clustering on the feature correlation matrix
- [x] Constructed feature correlation network graph
- [x] Evaluated feature redundancy and feature grouping
- [x] Selected an initial reduced feature set for the Range Detection Engine

### Review 

- [x] Reviewed statistical meaning of Pearson vs Spearman correlation
- [x] Examined correlation behavior among volatility‑based indicators
- [x] Analyzed structural feature clusters using hierarchical clustering
- [x] Interpreted correlation network to identify redundant feature groups
- [x] Evaluated stability vs diversity trade‑off when selecting representative features

_______
## 📚 What I Learned

- Correlation matrices help reveal overlapping information between engineered features.
    
- Different volatility indicators often measure similar underlying phenomena.
    
- Indicators derived from the same statistical component tend to cluster together.
    
- Hierarchical clustering provides a systematic way to detect feature families.
    
- Effective feature selection balances **statistical stability** and **information diversity**.

_______
## 💡 Key Concepts

- **Pearson Correlation:** Measures linear relationships between variables.
- **Spearman Correlation:** Measures monotonic relationships and is more robust to non‑linear structures in financial data.
- **Feature Clustering:** Grouping features based on similarity to identify redundant indicators.
- **Information Diversity:** Selecting features that capture different statistical aspects of market behavior.
- **Regime Detection:** Identifying structural market states (range vs expansion) rather than predicting direction.

____________
## 🐛 Problems & Solutions

- **Problem1:** Multiple volatility indicators showed moderate to high correlation, making it unclear which features provided unique information.  
- **Solution:** Used hierarchical clustering and correlation network visualization to identify feature families and select representatives.

- **Problem2:** Difficulty deciding between `range_rel_16` and `range_rel_48` as the representative of candle range compression.  
- **Solution:** Compared stability and correlation profiles; `range_rel_48` was selected for its smoother behavior and lower overall correlation with other features.

- **Problem3:** Risk of losing multi‑scale market information when reducing the feature set.  
- **Solution:** Balanced the final feature selection across horizons by keeping both short‑term (`atr_rel_16`) and mid‑term (`std_rel_48`, `range_rel_48`) signals.

_________
## 🎯 Tomorrow's Focus

- Analyze feature distributions and statistical ranges
- Normalize selected features for comparability
- Design the first aggregation method for the **Range Score (0–100)** 
