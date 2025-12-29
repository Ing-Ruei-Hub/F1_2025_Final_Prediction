
# 🏎️ F1 2025 Bayesian Championship Model

> Hierarchical Bayesian model for predicting Formula 1 race outcomes using PyMC


[📊 View Live Dashboard](https://ing-ruei-hub.github.io/F1_2025_Final_Prediction/)

---

## 🎯 Project Overview

This project uses a hierarchical Bayesian model to predict the 2025 F1 Abu Dhabi Grand Prix results, the championship-deciding finale.

**Key Results:**
- **MAE**: 2.53 positions
- **Accuracy**: 65% predictions within ±2 positions  
- **Successfully predicted**: Verstappen win (P3.98 → P1)
- **Championship outcome**: Correctly predicted Norris would secure title with P3

---

## 📊 Model Architecture

```
y ~ Normal(μ, σ)
μ = α + β_team + γ_driver + ε_race + Σ λᵢ·Xᵢ
```

**Components:**
- **α**: Baseline position
- **β**: Team/car performance (10 teams)
- **γ**: Driver skill (20 drivers)  
- **ε**: Race-specific effects
- **λ**: 6 feature coefficients (qualifying, points, pace, weather, reliability, form)

---

## 📈 Key Findings

### Team Rankings (β effects)
1. 🥇 McLaren: -2.591 (Fastest)
2. 🥈 Red Bull: -1.349
3. 🥉 Mercedes: -1.314
4. Ferrari: -1.024
5. Haas: +0.051

### Feature Importance (λ coefficients)
- **Qualifying (λ₁ = 2.360)** ⭐ Most important!
- Recent Form (λ₆ = 0.366)
- Driver Points (λ₂ = 0.332)
- Weather (λ₄ = 0.003) - Minimal impact

---

## 🛠️ Tech Stack

**Backend:**
- Python, PyMC, ArviZ, Pandas, NumPy

**Frontend:**  
- React, Tailwind CSS, Custom SVG Charts

**Method:**
- MCMC (1500 samples × 4 chains)
- Hierarchical Bayesian modeling

---

## 📊 Dataset

- **Training**: 459 observations (23 races × 20 drivers)
- **Validation**: Abu Dhabi GP 2025
- **Features**: Qualifying, points, pace, weather, reliability, form

---