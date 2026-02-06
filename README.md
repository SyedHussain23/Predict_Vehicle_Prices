# 🚗 Vehicle Price Prediction using Machine Learning

This project builds an end-to-end **machine learning regression system** to predict **vehicle selling prices** based on technical specifications and descriptive attributes.  
It demonstrates a complete ML workflow including **EDA, preprocessing, feature engineering, model training, evaluation, and prediction**.

---

## 📌 Project Overview

- **Problem Type:** Regression
- **Domain:** Automotive / Pricing Analytics
- **Goal:** Predict vehicle price accurately from structured and unstructured attributes
- **Models Used:** Random Forest Regressor, LightGBM Regressor
- **Best Model:** Random Forest Regressor

---

## 📊 Dataset

- **Source:** Vehicle listing dataset
- **Records:** 1,002 vehicles
- **Target Variable:** `price`
- **Feature Types:**
  - Numerical: year, mileage, cylinders, doors
  - Categorical: make, model, fuel, transmission, body, colors
  - Text: description, name

### Data Characteristics
- Missing values present in price, mileage, cylinders, colors, description
- Target variable is **right-skewed**
- High-cardinality categorical features

---

## 🔍 Exploratory Data Analysis (EDA)

Key insights:
- Newer vehicles generally have higher prices
- Mileage negatively correlates with price
- Vehicles with more cylinders tend to be more expensive
- Fuel type and transmission influence pricing
- Outliers detected in mileage and price

EDA techniques used:
- Histograms
- Scatter plots
- Box plots
- Feature-wise comparisons

---

## 🔧 Data Preprocessing

- **Missing Values**
  - Numerical → Median imputation
  - Categorical → Most frequent value
  - Target (`price`) → Median imputation

- **Feature Scaling**
  - StandardScaler applied to numerical features

- **Encoding**
  - OneHotEncoder used for categorical features
  - `handle_unknown='ignore'` to prevent inference errors

- **Pipeline**
  - ColumnTransformer + Pipeline used for clean preprocessing

---

## 🧠 Feature Engineering

New features created:
- **Vehicle Age** = Current Year − Vehicle Year
- **Description Word Count** (text complexity signal)
- **Make Extraction** from vehicle name

Final dataset:
- **2014 features after encoding**
- Supports non-linear learning

---

## 🧪 Model Training

### Models Evaluated
- Random Forest Regressor ✅
- LightGBM Regressor

Train-test split:
- **80% Training**
- **20% Testing**

---

## 📈 Model Evaluation

### 🔥 Random Forest Regressor (Best Model)

- **MAE:** \$3,852  
- **MSE:** 44,794,054  
- **R² Score:** **0.82**

### LightGBM Regressor
- **MAE:** \$5,217  
- **MSE:** 55,458,917  
- **R² Score:** 0.78

➡️ **Random Forest outperformed LightGBM across all metrics**

---

## 🔮 Price Prediction

The trained Random Forest model predicts prices for unseen vehicles.

**Example Predictions:**
[31572.38, 40717.47, 40552.83, 54939.23, 47485.55]

---


Predictions represent estimated vehicle selling prices in USD.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|-----|--------|
| Python | Programming |
| Pandas / NumPy | Data processing |
| Scikit-learn | ML models & pipelines |
| LightGBM | Gradient boosting |
| Matplotlib / Seaborn | Visualization |
| Jupyter Notebook | Experimentation |

---

## 🚀 How to Run

```bash
git clone https://github.com/SyedHussain23/Predict_Vehicle_Prices.git
cd Predict_Vehicle_Prices
pip install pandas numpy scikit-learn matplotlib seaborn lightgbm
jupyter notebook Predict_Vehicle_Prices.ipynb
```

---

## 🔮 Future Improvements
- Hyperparameter tuning for Random Forest
- Feature importance visualization
- XGBoost / CatBoost comparison
- Outlier handling with robust loss
- Deployment as a price prediction API

---

👨‍💻 Author

**Syed Hussain Abdul Hakeem**

- LinkedIn: https://www.linkedin.com/in/syed-hussain-abdul-hakeem
- GitHub: https://github.com/SyedHussain23

---

📄 License

This project is open source and available under the MIT License.

---

⭐ Show Your Support

If you found this project useful, consider giving it a ⭐.
