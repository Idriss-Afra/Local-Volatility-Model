# Local Volatility Model

A quantitative finance repository focused on stripping the **equity local volatility surface** from listed equity option data.

This project combines **SVI total variance calibration**, **Dupire local volatility extraction**, and **PDE-based option pricing under the local volatility framework**.

---

## Repository Structure

```text
Local-Volatility-Model/
├── Local Volatility Model.ipynb
```

---

## Project Overview

This notebook focuses on the **Local Volatility model** for equity derivatives.

It starts by constructing a smooth **implied total variance surface** from market option data through the **SVI model**. Beyond fitting the market smile, the SVI layer helps remove arbitrage inconsistencies, regularize the implied variance surface, and provide the smooth derivatives required for a more stable stripping of the **local volatility surface** through the **Dupire formula**.

The resulting local volatility surface is then embedded in a **PDE pricing framework**.

The local volatility PDE repricing of market quotes provides a direct measure of calibration quality. In this implementation, all repriced options differ by less than **5%** from their market prices, while **128 out of 142 options (about 90%)** show an error below **1%**.

---

### Market Data

The `MarketData/` folder includes the market inputs required for the calibration and repricing workflow.

- `CAC40_MarketData_12022025.csv` — market option data
- `CAC40_SVI_12022025.csv` — SVI-calibrated parameters
- `EURIBOR6M_ZCRates_12022025.csv` — zero-coupon rates used for discounting and forward-related calculations

Users can replace the sample input files with their own market data, provided that the CSV files keep the same structure as the ones included in `MarketData/`.  
To run the notebook correctly, the current column layout and overall file format must be respected.

---

## Example Output

**CAC40 Local Volatility Surface**:

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/30d9eea9-23ab-4328-8891-48ec290b5478" />

---

## Best use case

Use this notebook when working with **equity option market data** and building a **local volatility surface** for calibration, analysis, or local volatility PDE-based pricing.

---

## How to Use

Clone the repository:

```bash
git clone https://github.com/Idriss-Afra/Local-Volatility-Model.git
cd Local-Volatility-Model
jupyter notebook
```

Then open:

* `Local Volatility Model.ipynb`

---

## Author

**Idriss Afra**
