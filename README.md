# Simulation Study on Classification Algorithm Performance

This folder contains the **simulation study** conducted as part of the master’s thesis to evaluate the performance of various classification algorithms under different data distribution scenarios.

---

## 📘 Overview

In this section, a simulation study was carried out using **Python** to assess the performance of classification algorithms under **six different scenarios**.  
The sample size was set to **n = 1000**.

- **Dependent variable (Y):** Binary categorical variable  
- **Independent variable (X):** Continuous and/or categorical, depending on the scenario  

### 🎯 Scenarios
- **Scenarios 1–3:** X is continuous  
- **Scenarios 4–6:** X includes both continuous and categorical variables  

The dependent variable was generated from a **Bernoulli distribution** with the following probabilities:
- `p = 0.5` → balanced data  
- `p = 0.3`, `p = 0.2` → imbalanced data  

Independent variables were generated from different distributions:
- Multivariate Normal  
- Log-normal  
- Multivariate t  
- Gamma-t mixture distributions  

Noise variables were added from a multivariate normal distribution (mean = 0, covariance = I) to represent measurement errors.

Each scenario was **repeated 1000 times**, and the following performance metrics were calculated:
- Accuracy  
- Precision  
- Recall  
- F1-Score  

---

## 📊 Results and Discussion

The simulation results demonstrate how the underlying data distribution affects classification model performance.

| **Distribution Type** | **Best Performing Models** |
|------------------------|----------------------------|
| Multivariate Normal | Logistic Regression, Naive Bayes, SVM |
| Log-normal | Random Forest, Gradient Boosting |
| t-Distribution | SVM, Naive Bayes |
| Gamma-t Mixture | SVM, Gradient Boosting, Random Forest |


The findings highlight the **critical role of data distribution** in model selection and algorithmic success.

- Under **multivariate normal distribution**, linear models such as **Logistic Regression** and **Naive Bayes** performed best, supporting the use of linear methods for normally distributed data.  
- For **log-normal** and **Gamma-t mixture** distributions, **tree-based methods** (Random Forest, Gradient Boosting) showed superior performance, indicating their ability to capture nonlinear relationships effectively.  
- For **t-distributed data**, overall model performance decreased, but **SVM** and **Naive Bayes** remained relatively robust.

Class imbalance and the inclusion of categorical variables tended to reduce **F1-scores**, particularly in skewed datasets.  
However, **tree-based models** exhibited greater **resilience** to class imbalance and data complexity, producing more consistent results.  

Overall, considering both the **distributional characteristics** of the data and the **class balance** is essential for achieving optimal classification performance.
