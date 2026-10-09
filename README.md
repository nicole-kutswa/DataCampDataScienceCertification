# Predicting Recipe Popularity | Data Science Project
## Project Overview

This project explores recipe data to identify patterns associated with high website traffic and develop machine learning models that predict whether a recipe is likely to attract high traffic.

The project was developed as part of my DataCamp Data Scientist certification. It focuses on using data analysis and predictive modelling to support business decisions at Tasty Bytes, a recipe-focused platform seeking to increase website engagement and subscriptions.

The analysis covers data validation, data cleaning, exploratory data analysis (EDA), model development, and performance evaluation. The findings are used to recommend how predictive analytics could support recipe selection and homepage promotion.

## Business Problem

Tasty Bytes wants to increase website traffic and grow subscriptions by featuring recipes that are more likely to attract visitors.

However, selecting recipes based on intuition alone may not consistently produce the desired results. A data-driven approach could help the business identify promising recipes before featuring them on its homepage.

The project addresses the following question:

Can recipe characteristics be used to predict whether a recipe is likely to generate high website traffic?

The business set a target of at least **80%** prediction accuracy.

### Objectives
* Validate the dataset and address missing or inconsistent values.
* Explore recipe characteristics and investigate patterns associated with website traffic.
* Prepare the data for machine learning.
* Develop and compare classification models.
* Evaluate model performance using multiple metrics.
* Translate the findings into practical business recommendations.
  
[Dataset](recipe_site_traffic_2212.csv)

The dataset contains recipe information, including:

| Variable |	Description |
| :--- | :---|
| recipe	| Recipe identifier |
| calories	| Calorie content | 
| carbohydrate |	Carbohydrate content |
| sugar |	Sugar content |
| protein	| Protein content |
| category	| Recipe category |
| servings |	Number of servings |
| high_traffic	| Indicates whether a recipe generated high traffic | 

> The nutritional variables and recipe characteristics were used as potential predictors, while high_traffic was the target variable.

### Methodology
**1. Data Validation and Cleaning**

The dataset was checked for missing values, inconsistent categories, and formatting issues.

Key preparation steps included:

* Imputing missing nutritional values using the mean of their respective columns.
* Handling missing high_traffic values and converting the target into binary values: 1 for high traffic and 0 for not high traffic.
* Standardizing recipe categories and cleaning the servings column.
* Using assertions to validate numerical values and check data conditions.

> Missing target values were treated as not high traffic for this analysis. This assumption is a limitation because missing labels do not necessarily confirm that a recipe generated low traffic.

**2. Exploratory Data Analysis**

Exploratory analysis was used to examine recipe characteristics, distributions, and potential relationships with website traffic.

The analysis aimed to identify patterns that could inform recipe promotion and help guide feature selection for the predictive models.

**3. Data Preprocessing**

Before model training:

* Selected recipe characteristics and nutritional variables as input features.
* Encoded categorical variables into a numerical format.
* Split the dataset into training and testing sets using stratified sampling to preserve the target class proportions.
  
**4. Predictive Modelling**

Three classification algorithms were developed and compared:

* `Logistic Regression`: Used as a baseline classification model.
* `Decision Tree`: Used to identify patterns in the relationships between recipe characteristics and traffic.
* `Random Forest`: Used to combine multiple decision trees for classification.

**5. Model Evaluation**

The models were evaluated using:

`Accuracy`: The proportion of all predictions that were correct.
`Precision`: The proportion of recipes predicted as high traffic that actually generated high traffic.
`Recall`: The proportion of actual high-traffic recipes correctly identified.
`F1-score`: A combined measure of precision and recall.
`ROC-AUC`: A measure of how well the model distinguishes between the two target classes across classification thresholds.
Results

> Logistic Regression achieved the strongest overall performance among the three models tested.

| Evaluation Metric	| Logistic Regression	| Decision Tree	| Random Forest |
| :--- | :--- | :--- | :--- |
| Accuracy	| 74.68%	| 65.40%	| 71.31% |
| Precision	| 83.33%	| 73.48%	| 81.67% |
| Recall	| 72.92%	| 67.36%	| 68.06% |
| F1-score	| 77.78%	| 70.29%	| 74.24% |
| ROC-AUC	| 84.89%	| 64.73% |	81.75% |


**Key Findings**
Logistic Regression was the best-performing model across the evaluation metrics considered.
> Its accuracy of 74.68% fell short of the business target of 80% by 5.32 percentage points.
> Its precision of 83.33% indicates that most recipes predicted as high traffic were correctly classified in the test set.
The results suggest that recipe characteristics may provide useful predictive information, but further validation and improvement are needed before practical deployment.
Business Recommendations

Based on the model evaluation, the following actions are recommended:

1. **Use predictions as decision support**. Consider the model's predictions alongside editorial judgement and other business considerations when selecting recipes for homepage promotion.
2. **Improve model performance**. Investigate additional relevant features, review data quality, and test alternative model settings to work towards the 80% accuracy target.
3. **Monitor actual engagement**. Compare predictions with observed website traffic and regularly evaluate accuracy, precision, and recall.
4. **Measure business impact**. Test whether model-informed recipe selection improves website engagement and subscriptions rather than assuming that better predictions automatically produce business growth.

_Limitations_
* The best model did not meet the target accuracy of 80%.
* Missing target values were treated as not high traffic, which may introduce label inaccuracies.
* Predictive performance does not establish that a recipe characteristic causes higher traffic.
* The analysis predicts high traffic, but the effect of using these predictions on subscriptions has not been established.

### Tools and Technologies
* Python
* Pandas and NumPy
* Matplotlib and Seaborn
* Scikit-learn
* Jupyter Notebook / DataCamp DataLab
* Microsoft power point


### Conclusion

This project demonstrates how data validation, exploratory analysis, and machine learning can be combined to investigate a practical business problem.

Logistic Regression outperformed the Decision Tree and Random Forest models in the evaluation conducted. Although the model did not reach the 80% accuracy target, its precision and ROC-AUC results indicate potential for further development as a decision-support tool.

Future work should focus on improving predictive performance, validating assumptions about missing data, and testing whether model-informed recipe promotion leads to measurable improvements in website engagement and subscriptions.

Author: Nicole Kutswa

GitHub: [nicole-kutswa](https://github.com/nicole-kutswa)

LinkedIn: [nicole-kutswa](https://www.linkedin.com/in/nicole-kutswa/)

_This project was completed as part of the DataCamp Data Scientist certification._
