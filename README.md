# 📈 Method of Least Squares for Time Series Stationarity

This project applies the **Method of Least Squares** to extract the stationary version of a non-stationary time series dataset with a clear trend component and no seasonal behavior.

---

## 🎯 Objective

- To select a suitable time series dataset with a **trend** component and **no seasonality**
- To apply the **Method of Least Squares** iteratively to extract a **stationary version** of the series

---

## 📁 Dataset

- **Source**: U.S. Census Bureau via **Federal Reserve Economic Database (FRED)**
- The dataset shows a consistently increasing trend with no evident seasonal pattern, making it ideal for modeling an **additive time series**.

---

## 🧪 Key Steps

### 1. **Data Import & Time Series Conversion**
- The dataset is imported and converted into a **time series object** in R.

### 2. **Visualization**
- A time series plot is generated.
- **Observation**: The series shows a **clear upward trend** and **random noise**, with **no repetitive seasonal patterns**.

### 3. **Stationarity Check - ADF Test**
- **Null Hypothesis (H₀)**: The data is **non-stationary**
- **Alternative Hypothesis (H₁)**: The data is **stationary**
- **Result**: ADF test p-value = `0.4593` → **Fail to reject H₀** → Data is non-stationary

---

## 🔁 Extracting Stationarity Using Method of Least Squares

To transform the data into a stationary series:
1. A **first-order time variable** is created.
2. The data is fit into a **linear regression model** using this time variable.
3. The **residuals** from the model are extracted and tested for stationarity using the ADF test.

### ✳️ Iterative Process:
- Each time, a **higher-order time variable** (quadratic, cubic, etc.) is introduced to improve the model.
- After each model fitting, the residuals are re-tested for stationarity.

### ✅ Final Result:
- **Stationarity was achieved at the 6th level** of model fitting.
- ADF test p-value = `0.0312` → **Reject H₀** → Residuals are stationary

---

## ✅ Conclusion

- The original time series was **non-stationary** with a trend component.
- By applying the **Method of Least Squares** and modeling up to the **6th order polynomial trend**, the residuals became **stationary**.
- Final ADF test p-value = `0.0312` confirms stationarity.

---

## 🛠️ Tools & Technologies

- R Programming
- ADF Test (`tseries` package)
- Time Series Plotting
- Polynomial Regression for Detrending

---

## 📌 How to Run

1. Clone the repository or download the `.R` or `.Rmd` file.
2. Open in **RStudio**
3. Install necessary packages:
   ```R
   install.packages("tseries")
4. Run the script step-by-step to view model fitting and ADF results.

💡 Author Notes
This project was completed as part of my Master’s coursework to demonstrate understanding of time series transformation techniques and the use of least squares regression in stationarity extraction.

