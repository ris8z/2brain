---
date: 2025-01-20 
tags: 
    - CSC1044
hubs: 
    -   "[[2025-01-19_CSC1044-Machine-Learning|CSC1044 Machine Learning]]"
---

# data and method of ML paper on crops


## Dataset Description

### Structure
The dataset used in this research has **2200 rows and 8 columns**.
It consists of seven key features and one target variable: the crop type. These features are:

- **N, P, K**: The levels of nitrogen, phosphorus, and potassium in the soil, measured on a ratio scale.
- **Temperature**: Measured in degrees Celsius, an interval variable.
- **Humidity**: A percentage, also on a ratio scale.
- **pH**: The soil’s acidity level, an interval variable.
- **Rainfall**: Precipitation in millimeters, measured on a ratio scale.

Finally, the **crop type** serves as the target variable,
and it’s a nominal category, representing the recommended crop for the specified conditions.

### Methods Used

#### **Feature Selection**
- The authors applied a **filter method using the Variance Inflation Factor (VIF)** to reduce multicollinearity.
- Relevant features identified: **Temperature, Humidity, pH, and Rainfall**.

#### **Data Splitting**
- The dataset was divided into **67% for training** and **33% for testing**.
- No advanced techniques like cross-validation were used.

#### **Data Aggregation**
- The crop labels were grouped into broader categories (e.g., cereals or legumes) to simplify classification.

### Suggested Improvements

- **k-Fold Cross-Validation**: Ensures a more robust evaluation of the model by utilizing all data for both training and testing.
- **Data Augmentation**: Methods like **SMOTE** or synthetic data generation could address class imbalance and enhance dataset richness.

These improvements would make the results more reliable and better suited for real-world agricultural applications.

---

## Machine Learning Algorithms

This study focuses on a classification problem, aiming to predict the most suitable crop based on soil and environmental conditions.

### **Top 5 Algorithms Tested**

1. **Bayes Net**:
   - Builds a probabilistic network.
   - Achieved the **highest accuracy: 99.59%**.

2. **Naïve Bayes Classifier**:
   - A simple yet effective method assuming feature independence.
   - Accuracy: **99.46%**.

3. **Random Forest**:
   - Combines predictions from decision trees.
   - Improved to **97.32% accuracy** after feature selection.

4. **Hoeffding Tree**:
   - Efficiently processes data incrementally.
   - Accuracy: **99.46%**.

5. **Multilayer Perceptron (MLP)**:
   - A neural network capturing non-linear relationships.
   - Accuracy: **97.72%**.

---

### Suggested Algorithmic Improvements

- **Parameter Tuning**:
  - Use **Grid Search** or **Random Search** to optimize parameters such as:
    - For Random Forest: Number of trees, maximum depth.
    - For MLP: Number of neurons, learning rates.
    - For SVM (if included): Kernel type (RBF, linear), parameter \( C \).

- **Tools for Automation**:
  - Use frameworks like **scikit-learn**, **Optuna**, or **Hyperopt** for tuning and automation.

## General Observation
The study focuses more on modifying the **data** than customizing the algorithms. While several algorithms were tested, parameter tuning (critical for improving performance) was not conducted.

---

