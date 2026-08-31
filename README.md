# 📉 Customer Churn Survival Analysis: Predicting User Retention with XGBoost-Cox

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![XGBoost](https://img.shields.io/badge/XGBoost-Survival_Cox-red.svg)
![SHAP](https://img.shields.io/badge/SHAP-Interpretability-orange.svg)
![Lifelines](https://img.shields.io/badge/Lifelines-Kaplan_Meier-success.svg)

## 📌 Business Objective
**KKBOX**, Asia's leading music streaming service, operates on a freemium model heavily dependent on accurately predicting the churn of paid users. Traditional binary classification models fail to capture *when* a user will churn. 

This project re-frames customer churn as a **Time-to-Event (Survival) Analysis** problem. By applying epidemiological and biostatistical methodologies to business telemetry, this model not only predicts the probability of churn but also estimates the expected lifespan of a subscription, enabling highly targeted, time-sensitive retention campaigns.

## 🔬 Methodology & Tech Stack
- **Data Engineering:** Data cleaning, missing value handling (sparsity-aware architecture), and longitudinal aggregation using `Pandas` and `NumPy`.
- **Survival Analysis (Kaplan-Meier):** Applied `lifelines` to estimate global survival probabilities and identify critical drop-off periods in the customer lifecycle.
- **Predictive Modeling (XGBoost-Cox):** Implemented a Gradient Boosting model with a Cox Proportional Hazards objective (`survival:cox`) to predict user risk scores over time.
- **Model Interpretability (SHAP):** Extracted feature importance and directional impact using SHAP values to explain the drivers of churn at a granular level.

## 💡 Actionable Business Insights
Based on the SHAP values and survival curves, the model identified four critical areas for intervention:

1. **The "Short-Term Plan" Paradox:** Short-term plans (weekly/monthly) show lower drastic churn due to conscious flexibility. *Strategy:* Design retention incentives just before the first billing cycle ends, and implement aggressive onboarding for quarterly/annual plans to reduce renewal shock.
2. **Auto-Renewal Friction:** Auto-renewal exposes the "moment of truth" (declined cards, insufficient funds). *Strategy:* Implement a "smart retries" system and automated pre-billing email notifications to prevent passive churn due to payment friction.
3. **Payment Gateway Frictions:** Offline convenience store payments or high-friction bank gateways force manual renewals, elevating drop-offs. *Strategy:* Offer a one-time discount on the next invoice to incentivize migration toward native, low-friction payment gateways (e.g., direct credit card billing).
4. **The Onboarding Window (`dias_desde_registro`):** Churn risk is non-linear. The time elapsed from app discovery to premium conversion is a critical maturity point. *Strategy:* If a user hasn't engaged with core musical content early on, trigger personalized content recommendations to prevent platform fatigue.

## 📂 Repository Structure
```text
├── data/                   # (Ignored in git) Kaggle dataset files
├── notebooks/
│   └── KKBox_Churn_Survival_Analysis.ipynb  # Core analysis and modeling
├── README.md               # Project overview
└── requirements.txt        # Python dependencies

🚀 How to Run
Clone the repository:
´´´git clone [https://github.com/yourusername/kkbox-churn-survival.git](https://github.com/yourusername/kkbox-churn-survival.git)´´´

Install dependencies:
´´´pip install -r requirements.txt´´´

Download the data from the Kaggle KKBox Churn Prediction Challenge and place it in the data/ folder.

Run the Jupyter Notebook in the notebooks/ directory.

👨‍💻 About the Author
Quantitative Researcher & Data Analyst

Specializing in biostatistics, machine learning, and complex data processing. I bridge the gap between rigorous statistical methodologies and actionable business intelligence.
