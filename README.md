# ☀️ Solar Power Prediction Using Machine Learning
- ## 📓 Google Colab Notebook

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]https://colab.research.google.com/drive/1APYmO93QkaoVJIEDzbeh8w7lGATOPJgw?usp=sharing

---
## 📌 Project Overview

Solar power generation depends on environmental factors such as solar irradiation, ambient temperature, module temperature, and time of day. These factors continuously change, resulting in fluctuations in electricity generation.

This project uses Machine Learning techniques to predict solar inverter AC power generation based on weather conditions, historical measurements, and time-related features.

The main objective is to build and evaluate regression models that can estimate solar power generation, compare their performance, and identify important factors influencing energy production.

## 🎯 Objectives

- Analyze solar power generation and weather datasets using Exploratory Data Analysis (EDA).
- Perform data cleaning, preprocessing, and feature engineering.
- Identify relationships between weather conditions and AC power generation.
- Develop and compare multiple Machine Learning regression models.
- Optimize model performance through hyperparameter tuning.
- Evaluate models using MAE, RMSE, and R² score.
- Analyze feature importance and prediction errors.
- Explore applications in solar plant monitoring and predictive maintenance.

## 📂 Dataset

**Dataset:** Solar Power Generation Data

**Source:** [Kaggle – Solar Power Generation Data](https://www.kaggle.com/datasets/anikannal/solar-power-generation-data)

The dataset contains generation and weather sensor information from two solar power plants.

Four CSV files are used:

1. `Plant_1_Generation_Data.csv`
2. `Plant_1_Weather_Sensor_Data.csv`
3. `Plant_2_Generation_Data.csv`
4. `Plant_2_Weather_Sensor_Data.csv`

### Important Features

| Feature | Description |
|---|---|
| DATE_TIME | Date and time of measurement |
| AMBIENT_TEMPERATURE | Surrounding air temperature |
| MODULE_TEMPERATURE | Solar panel temperature |
| IRRADIATION | Solar radiation received |
| DC_POWER | DC power generated |
| AC_POWER | AC power generated (target variable) |
| PLANT_ID | Solar plant identifier |
| SOURCE_KEY | Inverter identifier |

## 🛠️ Technologies Used

- Python
- Google Colab
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- TensorFlow / Keras
- Joblib

## ⚙️ Project Workflow

### Week 1 – Problem Understanding and EDA

- Dataset loading and exploration.
- Dataset size and feature analysis.
- Missing value analysis.
- Outlier detection.
- Distribution analysis.
- Correlation analysis.
- Data preprocessing and feature engineering.
- Chronological training and testing split.

### Week 2 – Machine Learning and Optimization

Implemented and evaluated:

- Linear Regression
- Decision Tree Regressor
- K-Nearest Neighbors (KNN)
- Random Forest Regressor
- XGBoost Regressor
- Histogram Gradient Boosting
- Neural Network (MLP)

Optimization techniques:

- RandomizedSearchCV
- GridSearchCV
- Time-series cross-validation
- Feature engineering
- Early stopping
- Ensemble learning

### Week 3 – Model Evaluation and Comparison

Models were evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

Additional analysis included residual analysis, learning curves, and feature importance.

Two prediction approaches were compared:

1. **Weather-only estimation:** Uses weather and time-related features.
2. **Rolling short-term estimation:** Uses current weather conditions along with previous inverter power measurements.

### Week 4 – Interpretation and Deployment Insights

- Final model selection.
- Feature importance analysis.
- Solar plant performance comparison.
- Inverter-level performance analysis.
- Business insights and interpretation.
- Model limitations and future improvements.
- Model saving and deployment demonstration using Streamlit.

## 📊 Model Performance

### Final Selected Model

**Forecast HistGradientBoosting Regressor**

| Evaluation Metric | Result |
|---|---:|
| R² Score | 0.9555 |
| MAE | 24.02 kW |
| RMSE | 73.08 kW |
| Test Records | 40,964 |
| Cross-validation folds | 3 |

The selected model explains approximately 95.55% of the variance in the test data.

It was selected based on the lowest chronological cross-validation RMSE among the evaluated eligible models, without using the test set for model selection.

### Comparison of Prediction Approaches

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Forecast Ensemble | 23.75 | 72.71 | 0.9559 |
| Forecast HistGradientBoosting | 24.02 | 73.08 | 0.9555 |
| Weather-only Boosted Ensemble | 44.81 | 131.53 | 0.8557 |

**Note:** The forecast models use previous measured inverter power readings in addition to current weather. They perform rolling short-term estimation (nowcasting), not a genuine future 15-minute forecast. A weather-forecast data source would be required for that task.

## 🔍 Key Findings

- Solar irradiation is one of the most influential factors affecting power generation.
- Module temperature and time of day also contribute significantly to predictions.
- Solar power generation generally peaks around midday and becomes zero during nighttime.
- Differences in inverter performance can help identify equipment that may require inspection.
- Persistent negative prediction residuals can potentially support early identification of underperforming inverters.

## 🚀 How to Run the Project

### Option 1: Google Colab (Recommended)

1. Download or clone this repository.
2. Open the `.ipynb` notebook using Google Colab.
3. Download the dataset from Kaggle.
4. Upload the four CSV files if automatic downloading is unavailable.
5. Run all notebook cells sequentially.

### Option 2: Run Locally

Clone the repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd YOUR_REPOSITORY_NAME
```

Install the required libraries:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost tensorflow joblib scipy kagglehub streamlit python-docx
```

Open the notebook:

```bash
jupyter notebook
```

Run the notebook cells sequentially after making the dataset available.

## 📈 Deployment

A Streamlit demonstration application is generated in the notebook.

To run the application locally:

```bash
pip install streamlit
streamlit run app.py
```

## ⚠️ Limitations

- The dataset covers only 34 days and two solar plants.
- Seasonal patterns across different months and weather conditions are not represented.
- Prediction accuracy depends on the availability and quality of weather measurements.
- Performance on completely unseen solar plants requires further validation.
- A true day-ahead forecasting system requires future weather predictions.

## 🔮 Future Improvements

- Include data from more solar plants and longer time periods.
- Integrate real-time weather forecasting APIs.
- Explore LSTM and other time-series forecasting techniques.
- Use SHAP for explainable model predictions.
- Develop automated inverter anomaly detection.
- Implement model monitoring and periodic retraining.

## 👩‍💻 Author

**Ankitha Machagari**

B.Tech – Computer Science and Engineering

Symbiosis Institute of Technology, Hyderabad

## 📜 Acknowledgements

- Kaggle for providing the Solar Power Generation dataset.
- Scikit-learn, XGBoost, TensorFlow, and Python open-source communities.


⭐ If you find this project useful, feel free to explore the notebook and its implementation!
