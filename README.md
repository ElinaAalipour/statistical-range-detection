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

## Feature Set (v1)

### 1. ATR Compression
Measures volatility contraction relative to historical baseline.

- atr_rel_16
- atr_rel_48

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
Feature 1 (ATR Compression): Completed & Validated
Next: Rolling Standard Deviation Feature
