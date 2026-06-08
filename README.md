# Statistical Range Detection

## Objective
This project aims to statistically define ranging market conditions using quantitative volatility-based features.

---

## Research Question
How can ranging markets be statistically defined using measurable volatility compression signals?

---

## Market
EURUSD (H1 Timeframe)

---

## Methodology

Define volatility-based hypotheses  
Construct statistical features  
Validate features visually and statistically  
Perform correlation analysis and feature redundancy evaluation  
Select representative features based on stability and diversity  
Combine selected signals into a regime score

---
## Features

### ATR Compression ✅

Measures current volatility relative to historical ATR baselines.

**Purpose:** Detect volatility contraction and expansion regimes.

Features:

* atr_rel_16
* atr_rel_48

---

### Standard Deviation Compression ✅

Measures price dispersion relative to historical standard deviation baselines.

**Purpose:** Quantify changes in market variability.

Features:

* std_rel_16
* std_rel_48

---

### Candle Range Compression ✅

Measures individual candle-size contraction relative to historical candle ranges.

**Purpose:** Capture local price compression and expansion behavior.

Features:

* range_rel_16
* range_rel_48

---

### Bollinger Band Width Compression ✅

Measures price containment using normalized Bollinger Band Width.

**Purpose:** Detect periods where price becomes statistically compressed around its moving average.

Features:

* bb_rel_16
* bb_rel_48

### Feature Analysis & Selection ✅
After engineering 8 relative compression features, a full correlation and structural analysis was performed to evaluate feature redundancy and information overlap.

**Analysis Performed:**
* Pearson Correlation Matrix
* Spearman Correlation Matrix
* Cross-horizon correlation comparison (16 vs 48)
* Hierarchical feature clustering
* Feature correlation network visualization

### Key Findings:
* Indicators derived from similar statistical foundations (e.g., STD and Bollinger Width) showed strong correlation.
* Some short and mid-term horizons provided overlapping information.
* Volatility features naturally grouped into structural clusters.

### Selected Feature Set (v1 – Reduced Set):
* atr_rel_16
* std_rel_48
* range_rel_48

### These features were selected to balance:
* Signal stability (longer horizons)
* Information diversity (lower cross-correlation)
* Multi-scale market structure representation

---

## Feature Engineering Status

Completed Features:

* ATR Compression
* Standard Deviation Compression
* Candle Range Compression
* Bollinger Band Width Compression

Total Engineered Features:

* 8 Relative Compression Features

Current Stage:

* Feature Validation ✅
* Correlation & Redundancy Analysis ✅
* Initial Feature Selection ✅
* Range Score Design (In Progress)


---

## Visual Validation

### Price Behavior

![Price Validation](figures/price_validation.png)

### ATR Compression Behavior

![ATR Validation](figures/atr_validation.png)

---

## Key Insight

Volatility compression is not absolute; it is relative to historical context.

ATR features show clear separation between:
- ranging regimes (low relative ATR)
- trending regimes (high relative ATR)

---

## Project Status

### Completed

* Dataset acquisition and preprocessing
* Exploratory data analysis
* ATR Compression feature engineering
* Standard Deviation Compression feature engineering
* Candle Range Compression feature engineering
* Bollinger Band Width feature engineering
* Statistical validation
* Visual validation
* Full feature correlation analysis
* Feature clustering & redundancy evaluation
* Initial reduced feature set selection

### Current Phase

Range Score Design & Regime Quantification

### Upcoming Work

* Correlation analysis
* Feature redundancy evaluation
* Range Score design
* Market regime classification

### Research Question

How can ranging market conditions be statistically defined and quantified?

### Research Progression

**The project follows a structured quantitative research pipeline:**

1. Feature Engineering
2. Feature Validation
3. Feature Correlation & Structural Analysis
4. Feature Selection
5. Regime Score Construction
6. Market State Quantification
This ensures that the final Range Score is built on statistically justified and non-redundant components.
