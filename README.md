# Credit Card Customer Attrition Prediction

## Project Overview
This capstone project focuses on developing a data-driven approach to predict customer churn within a financial services dataset of **10,127 records**. By identifying "at-risk" users before they leave, the model provides a framework for targeted retention strategies and revenue protection.

## Technical Approach
* **Data Engineering:** Developed a pipeline in **Python** to handle categorical encoding and feature scaling.
* **Feature Selection:** Identified and removed redundant variables, such as `Avg_Open_To_Buy`, which had a perfect correlation ($r = 1.0$) with `Credit_Limit`.
* **Machine Learning:** Evaluated and compared four supervised models: **Logistic Regression, Decision Tree, K-Nearest Neighbors (KNN), and Support Vector Machine (SVM)**.

![Correlation Heatmap](https://github.com/user-attachments/assets/ff9dfdc0-4bec-4d91-bf8e-bb21969f2395)

*Caption: Pearson correlation analysis used to identify redundant features and leading indicators of churn.*

## Key Results
* **Top Performance:** The **Decision Tree** model achieved the highest test accuracy of **93.6%** on the reduced dataset.
* **Model Robustness:** The **SVM (RBF Kernel)** demonstrated superior class separation with an **AUC-ROC of 0.96**, proving highly effective at distinguishing churners.
* **Optimization:** Implemented a `max_depth=5` pruning strategy for the Decision Tree to effectively control overfitting.

 ![Accuracy Comparison](https://github.com/user-attachments/assets/d2039363-e696-4c70-8fc3-20b6c18bc182)

*Caption: Performance comparison across the four evaluated machine learning algorithms.*

## Summary of Performance Trend
A critical part of this study was observing how model performance changed when switching from a Full Dataset to a Reduced Dataset engineered to remove multicollinearity.

| Model | Full Dataset Accuracy | Reduced Dataset Accuracy | Trend |
| :--- | :--- | :--- | :--- |
| **Logistic Regression** | 89.7% | 89.7% | Stable |
| **Decision Tree** | 93.6% | **93.6%** | **Peak Performance** |
| **KNN (k = 6)** | 90.9% | 91.1% | Slight Increase |
| **SVM (RBF Kernel)** | 93.19% | 93.35% | Stable/Consistent |

**Analysis:** The consistency in results across both datasets confirms that removing redundant features enhanced model efficiency without sacrificing predictive power.

## Business Recommendations
1. **Targeted Intervention:** Use the model to identify the "at-risk" segment for personalized outreach and retention offers.
2. **Behavioral Monitoring:** Track **Total Transaction Count** and **Total Revolving Balance**, as these were identified as the strongest predictors of attrition.
3. **Strategic Efficiency:** Deploy the model using the **Reduced Feature Set** to reduce computational costs while maintaining high accuracy.

![Decision Tree](https://github.com/user-attachments/assets/23229251-9341-4208-83b2-64b795ac3b6c)

*Caption: Visualization of the Decision Tree logic used to classify at-risk customers.*

## Tools Used
* **Languages:** Python (Pandas, Scikit-Learn, NumPy)
* **Techniques:** Predictive Modeling, Feature Engineering, Multi-collinearity Analysis, Model Evaluation (AUC-ROC)
* **Environment:** Enginius / Jupyter Notebook
