---
date: 2025-01-20 
tags: 
    - CSC1044
hubs: 
    -   "[[2025-01-19_CSC1044-Machine-Learning|CSC1044 Machine Learning]]"
---

# ML on crops Presentations

----------

# Paper 1
## Title: Using machine learning for crop yield prediction in the past or the future
### Authors: Alejandro Morales, Francisco J. Villalobos

### Main Objectives:
- Develop machine learning models to predict sunflower and wheat yields using synthetic data.
- Analyze the effectiveness of algorithms with different data partitioning strategies and training periods.

### Methods:
1. **Synthetic Dataset**: Data generated using biophysical models (OilcropSun and Ceres-Wheat) to simulate 20 years of cultivation across 5 regions in Spain.
2. **Selected Features**: Climate data (temperature, solar radiation, rainfall), agricultural data (soil depth, sowing date, irrigation), and yield.
3. **Tested Algorithms**:
   - Regularized linear models (Lasso, Ridge)
   - Random Forest
   - Artificial Neural Networks (ANN)
4. **Data Partitioning Strategies**:
   - **Time-ordered**: Train on older data and test on more recent data.
   - **Randomized**: Random data splits.
5. **Evaluation Metrics**: RMSE (Root Mean Square Error), MAE (Mean Absolute Error), R².

### Results:
- Random Forest performed best with RMSE of 35-38% for time-ordered predictions.
- Neural networks showed variable performance (RMSE between 37% and 141%) and a tendency to overfit.
- Regularized linear models had the worst performance (RMSE of 64-65%).
- Randomized partitioning overestimated model performance compared to time-ordered splits.

---

# Paper 2
## Title: Crop Prediction Model Using Machine Learning Algorithms
### Authors: Ersin Elbasi et al.

### Main Objectives:
- Develop models to classify the most suitable crops based on environmental and historical data.
- Explore the impact of feature selection and label design on model performance.

### Methods:
1. **Real Dataset**: 2200 records from Kaggle with 22 crop types (e.g., apple, banana, rice) and 7 variables (nitrogen, phosphorus, potassium, temperature, pH, humidity, rainfall).
2. **Selected Features**: Reduced using Variance Inflation Factor (VIF) to eliminate multicollinearity.
3. **Tested Algorithms**:
   - Bayes Net
   - Naïve Bayes
   - Random Forest
   - Multilayer Neural Networks
4. **Evaluation**: Training/testing split (67%/33%), metrics: Accuracy, MAE, RMSE.
5. **Advanced Experiments**:
   - Grouping crops into general categories.
   - Analyzing the impact of different feature combinations.

### Results:
- Bayes Net achieved the highest accuracy (99.59%), followed by Naïve Bayes and Hoeffding Tree (99.46%).
- The most relevant features for accuracy were temperature, humidity, pH, and rainfall.
- Multilayer Neural Networks showed increasing accuracy (93% to 97.72%) with more training data.

---

# Comparison Between Papers

| **Characteristic**       | **Paper 1**                                                 | **Paper 2**                                           |
|---------------------------|------------------------------------------------------------|------------------------------------------------------|
| **Objective**             | Predict crop yields using regression models.               | Classify the optimal crop for specific conditions.   |
| **Data Type**             | Synthetic data from biophysical models.                    | Real data from Kaggle with crop type labels.         |
| **Main Algorithms**       | Random Forest, Neural Networks, Regularized Linear Models. | Bayes Net, Naïve Bayes, Random Forest, MLP.         |
| **Evaluation Metrics**    | RMSE, MAE, R².                                             | Accuracy, MAE, RMSE, build/test time.               |
| **Partitioning Strategy** | Time-ordered (future prediction) and randomized.           | 67% training, 33% testing (no cross-validation).     |
| **Key Results**           | Random Forest best for time-ordered; ANN prone to overfit. | Bayes Net most accurate; key features: temp, pH, etc. |
| **Applicability**         | Theoretical: evaluating algorithms on controlled data.     | Practical: recommendations for real crops.          |
| **Disadvantages**         | Synthetic data limits real-world applicability.            | Small, simplified dataset; needs more testing.       |

---

# Additional Concepts

## 1. Regularized Linear Models (Lasso, Ridge)
### What They Are:
- Linear models aim to find a line (or plane) that best describes the relationship between input variables (e.g., temperature, rainfall) and a target variable (e.g., crop yield).

### Problem:
- With too many variables (features), the model can become overly complex and perform poorly on new data (overfitting).

### Solution (Regularization):
- **Lasso**: Reduces coefficients (the weights of variables) and can set some to zero, effectively removing irrelevant variables.
- **Ridge**: Shrinks coefficients but keeps all variables.

### Intuition:
Lasso eliminates unnecessary "weight" (irrelevant features), while Ridge simplifies the model without dropping variables.

---

## 2. RMSE (Root Mean Square Error)
### What It Measures:
- The difference between predicted and actual values.

### How It Works:
1. Calculate the difference (error) between each prediction and the actual value.
2. Square each difference (to avoid negatives).
3. Take the average and then the square root.

### Why It’s Useful:
- Penalizes large errors more heavily, making it sensitive to big mistakes.

### Intuition:
It’s like an archer’s average score: big misses heavily impact the result.

---

## 3. MAE (Mean Absolute Error)
### What It Measures:
- The average of the absolute differences between predicted and actual values.

### How It Works:
1. Take the absolute value of each error.
2. Calculate the average.

### Why It’s Useful:
- Simpler to interpret and treats all errors equally.

### Intuition:
Like measuring how far each shot lands from the bullseye, treating all misses equally.

---

## 4. R² (Coefficient of Determination)
### What It Measures:
- How well the model explains the observed data (ranges from 0 to 1).
- **1**: Perfect explanation of data.
- **0**: No better than a simple average.

### How It Works:
- Compares the variance explained by the model to the total variance in the data.

### Why It’s Useful:
- Shows the percentage of variability in the data captured by the model.

### Intuition:
If you’re predicting fruit weight, an R² of 0.9 means the model explains 90% of the weight differences.

---

## 5. Multicollinearity and VIF
### What Is Multicollinearity?
- When two or more independent variables (e.g., rainfall and humidity) are strongly correlated, making it hard for the model to determine their individual effects.

### What Is VIF (Variance Inflation Factor)?
- A measure of how much a variable is correlated with others.
- **VIF = 1**: No correlation (perfect!).  
- **VIF 1-5**: Moderate correlation (acceptable).  
- **VIF > 10**: High correlation (problematic!).

### How to Use VIF:
1. Calculate VIF for each variable.
2. Remove or combine variables with high VIF.
3. Get a simpler, more reliable model.

