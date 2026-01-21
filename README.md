# Credit Card Customer Attrition Prediction

## Project Overview
This capstone project focuses on developing a data-driven approach to predict customer churn within a financial services dataset of **10,127 records**. By identifying "at-risk" users before they leave, the model provides a framework for targeted retention strategies and revenue protection.

## Technical Approach
* **Data Engineering:** Developed a pipeline in **Python (Pandas, Scikit-Learn)** to handle categorical encoding and feature scaling.
* **Feature Selection:** Identified and removed redundant variables, such as `Avg_Open_To_Buy`, which had a perfect correlation ($r = 1.0$) with `Credit_Limit`.
* **Machine Learning:** Evaluated and compared four supervised models: **Logistic Regression, Decision Tree, K-Nearest Neighbors (KNN), and Support Vector Machine (SVM) with an RBF kernel**.

![Correlation Heatmap](your_heatmap_filename.png)
*Caption: Pearson correlation analysis used to identify redundant features and leading indicators of churn.*

## Key Results
* **Top Performance:** The **Decision Tree** model achieved the highest test accuracy of **93.6%** on the reduced dataset.
* **Model Robustness:** The **SVM (RBF Kernel)** demonstrated superior class separation with high **AUC-ROC** values, proving its effectiveness at distinguishing between churners and non-churners.
* **Optimization:** Implemented a `max_depth=5` pruning strategy for the Decision Tree to effectively control overfitting and ensure high generalization on unseen data.

![Model Test Accuracy Comparison](your_accuracy_chart_filename.png)
*Caption: Performance comparison across the four evaluated machine learning algorithms.*

## Summary of Performance Trend
A critical part of this study was observing how the models behaved when switching from a Full Dataset to a Reduced Dataset (engineered to remove multicollinearity).

| Model | Full Dataset Accuracy | Reduced Dataset Accuracy | Trend |
| :--- | :--- | :--- | :--- |
| **Logistic Regression** | 89.44% | 89.59% | Stable/Slight Increase |
| **Decision Tree** | 93.45% | **93.60%** | **Peak Performance** |
| **KNN** | 89.24% | 88.99% | Stable |
| **SVM (RBF)** | 93.35% | 93.35% | Consistent |

**Analysis:** The consistency in results across both datasets proves that the feature selection process was successful. We maintained (and in the case of the Decision Tree, improved) accuracy while creating a more efficient, "lighter" model.

## Business Recommendations
1. **Targeted Intervention:** Use the model to identify the "at-risk" segment for personalized outreach and retention offers.
2. **Behavioral Monitoring:** Track **Total Transaction Count** and **Total Revolving Balance**, as the model identified these as the strongest predictors of attrition.
3. **Strategic Efficiency:** Deploy the model using the **Reduced Feature Set** to reduce computational costs without sacrificing predictive power.

![Decision Tree Logic](your_tree_structure_filename.png)
*Caption: Visualization of the Decision Tree logic used to classify at-risk customers.*

## Tools Used
* **Languages:** Python (Pandas, Scikit-Learn, NumPy)
* **Techniques:** Predictive Modeling, Feature Engineering, Multi-collinearity Analysis, Model Evaluation (AUC-ROC)
* **Environment:** Enginius / Jupyter Notebook
