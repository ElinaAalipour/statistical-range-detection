# Day 5: Rolling Standard Deviation Feature

### Project Work 

- [x] Implemented rolling standard deviation features:
- `std_16`
- `std_48`    
- `std_rel_16
- `std_rel_48`

- [x] Added Feature 2 outputs to the project dataset.
- [x] Generated and saved validation charts:
- `std_validation.png`    
- `std_distribution.png`
- [x] Created and saved `eurusd_h1_features_v2.csv`.
- [x] Performed correlation analysis between ATR Compression and Standard Deviation Compression features.
- [x] Published the first public research update on LinkedIn.
### Review

- [x] Visually validated feature behavior during ranging market conditions.
- [x] Evaluated whether lower price dispersion aligns with volatility compression.
- [x] Reviewed potential false positives and feature limitations.
_________
## 📚 What I Learned
- Standard deviation measures price dispersion around a rolling mean rather than candle range size.
    
- ATR and standard deviation capture related but non-identical aspects of market behavior.
    
- Low price dispersion is frequently observed during ranging market conditions.
    
- Relative features provide more context than absolute feature values.
    
- Feature validation requires both visual inspection and quantitative comparison.
_____
## 💡 Key Concepts

- Rolling Standard Deviation: Measures how far prices deviate from their local average over a rolling window.
    
- Price Dispersion: The spread of prices around an equilibrium level.
    
- Feature Correlation: A method for evaluating whether two features provide overlapping or complementary information.
_____
## 🐛 Problems & Solutions

- **Problem1:** Raw standard deviation values were difficult to interpret across different market environments.
- **Solution:** Created relative standard deviation features (`std_rel_16`, `std_rel_48`) to compare current dispersion against historical dispersion.

- **Problem2:** Validation charts became visually noisy when plotting the full dataset.
- **Solution:** Focused on representative samples and relative measures for clearer interpretation.

- **Problem3:** Uncertainty regarding whether standard deviation added unique information beyond ATR.
- **Solution:** Performed correlation analysis and found a moderate relationship (~0.70), suggesting partial overlap with additional independent information.
_______
## 🎯 Tomorrow's Focus

- Design Feature 3: Candle Range Compression.
- Define the hypothesis, interpretation, and limitations of candle-range-based compression.
- Implement and validate the next feature using the same research workflow.
