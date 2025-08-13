# Assignment_17.1 - Comparing Classifiers on Bank Marketing Data

## Project Summary
This project applies **four classification methods** — K‑Nearest Neighbors, Logistic Regression, Decision Trees, and Support Vector Machines — to a **Portuguese bank telemarketing dataset** from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/222/bank+marketing).  
The business goal: **predict whether a customer will subscribe to a term deposit** after a marketing call, enabling the bank to focus resources on the most promising leads.

We follow a **CRISP‑DM** approach:
1. **Business understanding** → Increase conversion rates & reduce wasted calls.
2. **Data understanding** → Explore class imbalance, key numeric/categorical features.
3. **Data preparation** → Cleaning, encoding, scaling, train/test split.
4. **Modeling** → Train/evaluate KNN, Logistic Regression, Decision Tree, SVM.
5. **Evaluation** → Compare performance via cross‑validation & tuned hyperparameters.
6. **Deployment recommendations** → Suggested model & business next steps.

---

## Modeling
- **Models evaluated:**  
  - K‑Nearest Neighbors (KNN)  
  - Logistic Regression  
  - Decision Tree Classifier  
  - Support Vector Machine (SVM)
- **Hyperparameter tuning:** GridSearchCV for each model.
- **Cross‑validation:** 5‑fold CV with multiple metrics (`roc_auc`, `f1`, `average_precision`).
- **Metric choice:** ROC‑AUC chosen as primary — handles imbalance, measures ranking power.
- **Interpretation:**  
  - Logistic Regression coefficients interpreted for odds directionality.  
  - Tree feature importances reviewed for top predictors.

---

## Results Summary

| Model                | Train Time (s) | Train Accuracy | Test Accuracy |
|----------------------|---------------:|---------------:|--------------:|
| Logistic Regression  | 0.047          | 0.8873         | 0.8874        |
| Baseline             | 0.000          | 0.0000         | 0.8873        |
| SVM                  | 35.783         | 0.8882         | 0.8864        |
| KNN                  | 0.025          | 0.8897         | 0.8774        |
| Decision Tree        | 0.359          | 0.9171         | 0.8643        |

**Observations:**
- Logistic Regression and SVM (RBF) achieved similar test accuracies, but SVM was significantly slower to train.
- Decision Tree had the highest training accuracy but dropped more on test → overfitting risk.
- Baseline accuracy (~88.7%) was similar to all other models.

---

## Notebook Access
View the full analysis and code in the [Jupyter Notebook](prompt_III.ipynb).

---
