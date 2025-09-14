# Marketing Mix Modeling with Mediation Assumption

This project implements a **Marketing Mix Model (MMM)** using a 2-year weekly dataset of media investments, price, promotions, followers, and revenue.  
The analysis explicitly incorporates the **mediation assumption** that **Google spend mediates the effect of social/display platforms (Facebook, TikTok, Snapchat) on revenue**.

---

## 📂 Project Structure

├── MMM_Mediation_Marketing_Mix_Modeling.ipynb # Main analysis notebook
└──README.md # Project documentation



---

## ⚙️ Setup Instructions

1. Clone or download the repo.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt


jupyter notebook MMM_Mediation_Marketing_Mix_Modeling.ipynb



📊 Methodology

Data Preparation

Handled weekly seasonality & long-term trends with time-series decomposition.
Addressed zero-spend weeks using imputation/flag variables.
Scaled/normalized features to stabilize regression.
Lagged features for carryover/adstock effects.

Modeling Approach

Implemented a two-stage mediation model:
Stage 1: Social/Display → Google Spend.
Stage 2: Google Spend + Direct Levers (Email/SMS, Price, Followers, Promotions) → Revenue.
Compared linear regularized regression (Lasso/Ridge) with tree-based models (XGBoost).

Validation

Used blocked time-series cross-validation (no look-ahead bias).
Residual analysis to test model stability.
Sensitivity checks for promotions and average price.

Causal Framing

Structured the DAG to respect mediator relationships.
Avoided direct leakage paths by not letting Facebook/TikTok/Snapchat enter Stage 2 directly.
Discussed back-door paths and collinearity risks.

📈 Results

Out-of-sample performance shows stable predictive accuracy.
Mediation results indicate:
Social platforms have significant indirect effects via Google spend.
Email/SMS campaigns show short-term direct uplift.
Price increases are negatively correlated with revenue (elasticity effects).
Promotions provide positive but temporary spikes.

📝 Deliverables

Notebook (reproducible code)
README.md (this file)

🚀 Insights & Recommendations

Invest in social/display primarily as upper-funnel drivers to stimulate search demand.
Google spend remains the strongest direct lever for revenue.
Manage promotions carefully to avoid eroding price integrity.
Consider follower growth and email/SMS as supporting retention channels.
