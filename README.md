# 🌞 Forecasting Mean Monthly Sunspots Using Prophet and XGBoost

### 📌 Situation
Sunspots are dark areas on the Sun's surface associated with intense magnetic activity. These phenomena follow a recognizable cyclic pattern, peaking roughly every 11 years, and are known to impact space weather and Earth's climate. This project explores the mean monthly sunspot data spanning from **1749 to 2020** to model and forecast future sunspot activity.

### 🎯 Task
The objective was to:
- Analyze long-term patterns and cycles in sunspot data.
- Develop robust forecasting models using both **Prophet** and **XGBoost**.
- Leverage **Bayesian Optimization** to fine-tune model hyperparameters for improved forecasting accuracy.
- Compare model performance across different forecast periods.

### 🔧 Action
- **Exploratory Data Analysis (EDA):**  
  Conducted preliminary analysis and identified clear cyclic behavior in the data. Peaks and troughs follow a roughly **10-year cycle**, with additional longer-term patterns over **30, 60, and 120 years**.
  
- **Modeling Approaches:**
  - **Prophet Model:**  
    Utilized Facebook's Prophet to model the time series, benefiting from its ability to handle seasonality and trends effectively.
  
  - **XGBoost Model:**  
    Developed a feature-based regression model using gradient boosting, incorporating time-based lag features and engineered cyclic components.
  
- **Hyperparameter Tuning:**
  - Implemented **Bayesian Optimization** to identify optimal parameters for both models, refining search spaces around promising configurations for better performance.

- **Evaluation:**
  - Models were evaluated using **Mean Absolute Error (MAE)** across different time slices to assess temporal stability and forecasting accuracy.

### ✅ Result

| Model     | Forecast Period       | MAE    |
|-----------|------------------------|--------|
| Prophet   | 1990 onward            | 43.69  |
| Prophet   | 2000 onward            | 37.86  |
| Prophet   | 2010 onward            | 25.65  |
| XGBoost   | 1990–2004              | 27.61  |
| XGBoost   | 2000–2014              | 39.47  |
| XGBoost   | 2010–2020              | 21.00  |

- The **XGBoost model** showed stronger short-term performance, particularly from **2010 to 2020**.
- The **Prophet model** excelled in capturing broader cyclic trends over long time spans.
- Bayesian Optimization significantly improved the performance of both models through intelligent hyperparameter tuning.

---

## 📁 Project Structure

```bash
.
├── data/                  # Raw and cleaned sunspot data
├── notebooks/             # Jupyter notebooks for EDA and modeling
├── models/                # Saved model artifacts
├── bayes_optimization/    # Scripts for Bayesian Optimization
├── README.md              # You're here!
