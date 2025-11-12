# Student Exam Performance Prediction

##  Project Overview
This project aims to predict **students' math exam scores** based on a combination of academic performance metrics and demographic attributes.  
By analyzing how reading and writing scores, along with socio-economic and educational background factors, influence math performance,  
this model provides valuable insights for improving student outcomes.

---

## Dataset Description
The dataset contains **no missing values** and includes:
- **5 categorical features**:  
  `gender`, `race/ethnicity`, `parental level of education`, `lunch`, `test preparation course`
- **2 continuous features**:  
  `reading score`, `writing score`
- **1 target variable**:  
  `math score`

The goal is to predict students’ **math score** based on the other features.

---

##  Project Objectives
1. Perform **exploratory data analysis (EDA)** to understand data patterns.  
2. Conduct **univariate, bivariate, and multivariate analysis** for deeper insights.  
3. Assess **multicollinearity and normality** of predictors to validate model assumptions.  
4. Apply **feature transformation** (Yeo–Johnson) to normalize skewed data.  
5. Interpret model explainability using **SHAP values**.

---

##  Exploratory Data Analysis

### Distribution Insights
- Reading and writing scores are **strongly correlated** with math scores.  
- Students whose parents have only a high school education tend to score lower in math.  
- The residuals of the linear model are approximately normal and homoscedastic for the training data.  

### Multicollinearity & ANOVA
- No collinearity was observed among the categorical variables.  
- ANOVA tests helped identify weaker predictors among highly correlated numerical features.

---

##  Model Development

###  Linear Regression
A baseline **Linear Regression** model was fitted after preprocessing and transformation.  
Residual analysis confirmed near-normal residual distribution and mostly homoscedastic patterns.

###  RidgeCV,LassoCV and ElasticNetCV
RidgeCV was used for **regularization** to handle minor multicollinearity and improve generalization.


---

##  Model Evaluation Metrics
Each model was evaluated on:
- **MAE** – Mean Absolute Error  
- **RMSE** – Root Mean Squared Error  
- **R² Score** – Coefficient of Determination  

All metrics were computed for both the training and test sets after inverse Yeo–Johnson transformation.

---

##  Model Explainability (SHAP)

###  SHAP Summary
SHAP (SHapley Additive exPlanations) values were used to interpret individual predictions.

#### Example Interpretation:
The SHAP plot below shows how each feature affects a single student's math score prediction:
- **Positive (pink)** values increase the prediction.
- **Negative (blue)** values decrease it.

Key drivers increasing the prediction include:
- Higher reading and writing scores  
- Having standard lunch  
- No test preparation course  
- Being male (in this case study)

Conversely, some ethnicity groups contributed slightly to lowering the prediction.

---


