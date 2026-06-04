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

The project follows a feature-driven research approach:

1. Define volatility-based hypotheses
2. Construct statistical features
3. Validate features visually and statistically
4. Combine multiple weak signals into a regime score

---
## Features

### ATR Compression ✅

Measures volatility contraction relative to historical ATR baselines.

Features:

- atr_rel_16
- atr_rel_48

---

### Standard Deviation Compression ✅

Measures return dispersion relative to historical volatility baselines.

Features:

- std_rel_16
- std_rel_48

---

### Candle Range Compression ✅

Measures candle-size contraction relative to historical candle ranges.

Features:

- range_rel_16
- range_rel_48

---

### Bollinger Band Width

Planned

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

Completed:

- ATR Compression
- Standard Deviation Compression
- Candle Range Compression

In Progress:

- Bollinger Band Width

Next:

- Feature Correlation Analysis
- Range Score Construction
