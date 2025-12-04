# 📈 Real Estate as a Fixed-Income Asset  
### *A Quantitative Term-Structure, Mortgage-Spread & Yield-Curve Analysis Engine*  
**Fixed Income Project**


![Profile Views](https://komarev.com/ghpvc/?username=anay-a-joshi&color=green)  


---

## 🚀 Overview  

This repository contains a **fully engineered, interactive analysis engine** that treats a residential property not as “just real estate,” but as a **leveraged fixed-income instrument**.

The project combines:

- **Yield-curve modeling (2005–2025)**  
- **Mortgage-spread construction and decomposition**  
- **OLS regression of mortgage spreads on Treasury term spreads**  
- **FRED-based data pipeline in Python**  
- **Custom time-series visualizations**  
- **A Web-based Presentation (Web-PPT) built in pure HTML/CSS/JS**

The goal is to present real estate through the same lens a fixed-income or macro desk would use to study **duration, term premia, and curve slope risk**.

---

## 🔧 Tech Stack & Methodology  

### Tech Stack

- **Python**: `pandas`, `statsmodels`, `matplotlib`  
- **Data Source**: Federal Reserve Economic Data, i.e., FRED (mortgage & Treasury series)  
- **Frontend**: Custom HTML / CSS / vanilla JS (no PowerPoint)  
- **Delivery**: GitHub Pages–ready Web-PPT

### Quant Focus

- Construct **mortgage spreads**:  
  - `spread_15_5  = 15Y FRM – 5/1 ARM`  
  - `spread_30_15 = 30Y FRM – 15Y FRM`  

- Construct **Treasury term spreads**:  
  - `ts_10_1 = 10Y – 1Y`  
  - `ts_30_1 = 30Y – 1Y`  

- Run two OLS regressions:

  **Model A**  
  15Y – 5/1 ARM = α + β₁·(10Y–1Y) + β₂·(30Y–1Y)

  **Model B**  
  30Y – 15Y   = α + β₁·(10Y–1Y) + β₂·(30Y–1Y)

- Interpret coefficients, R², and economic intuition in a **fixed-income framework**.

---

## 🏡 Real Estate as a Fixed-Income Security  

In this framework, the Tampa luxury property is treated like a bond:

- **Down payment + closing costs** → “Bond price”  
- **Net rental income** → “Coupon stream”  
- **Resale value / equity at exit** → “Redemption value”  
- **Mortgage** → Embedded leverage + path-dependent cash flows  
- **Refinancing / prepayment** → Embedded options  

This allows us to compute a **bond-equivalent IRR** and compare the property directly to **equities and long-term Treasuries** on a risk–return basis.

---

## 📊 Data & Regressions  

### Data (FRED Time Series)

- Mortgage rates:
  - `MORTGAGE5US`  → 5/1 ARM  
  - `MORTGAGE15US` → 15-year fixed  
  - `MORTGAGE30US` → 30-year fixed  

- Treasury yields:
  - `DGS1`  → 1-year  
  - `DGS10` → 10-year  
  - `DGS30` → 30-year  

**Sample window:**  
`2005-02` to `2025-06` (covers housing bubble, GFC, QE, normalization, pandemic, and inflation shock regimes).

### Key Insights

- **Model A (15Y – 5/1 ARM)** has a relatively **low R²**:  
  only a small fraction of this spread is explained by the curve slope alone.  
  The rest reflects **product design, funding costs, credit overlays, and prepayment behavior**.

- **Model B (30Y – 15Y)** has a **higher R²**:  
  the extra premium to lock in a **30Y fixed** vs **15Y fixed** is more tightly linked to the long-end slope of the curve, consistent with **duration and prepayment risk compensation**.

> If I wanted to push R² higher in a production environment, I would extend the factor set to include **swap spreads, MBS OAS, volatility surfaces, and macro/credit controls**, similar to what real mortgage/term-structure desks track.

---

## 📈 Visualizations  

The code produces:

- Time-series charts of:
  - **Mortgage spreads**: 15Y–5/1 ARM and 30Y–15Y  
  - **Treasury term spreads**: 10Y–1Y and 30Y–1Y  

- Clean, publication-style plots used directly in the Web-PPT:
  - **Spread time-series**
  - **Curve slope regimes**
  - **Regression summaries / diagnostics (via `statsmodels`)**

All graphs are **reproducible** by running the Python script in the repo.

---

## 🌐 Web-PPT (Interactive Presentation)  

Instead of PowerPoint, the project is delivered via a **custom interactive website**:

- Tabs for **Introduction, Property Choice, Cash Flows, Treasuries, Regressions**  
- Animated 3D intro and smooth transitions  
- Clickable, zoomable charts (image modal)  
- Organized “Question-by-Question” structure mirroring the assignment  
- Dark, quant-lab–style UI with a focus on readability and storytelling

This reflects how real quant & trading teams often present work:  
**as a live, code-backed artifact**, not static slides.

---
