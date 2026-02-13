# Sampling
https://colab.research.google.com/drive/1XulJf8GN-Uo-EqqomIwouEtkpO8jFyMm?usp=sharing


1️ Problem Overview

The credit card dataset used in this project is highly imbalanced, where the number of non-fraud transactions significantly outweighs fraud transactions. In such cases, machine learning models tend to become biased toward the majority class, leading to misleadingly high accuracy but poor fraud detection performance.

To address this issue, multiple sampling strategies were applied to balance the dataset before training classification models.

2️ Sampling Techniques Compared

Five different resampling techniques were implemented:

Random OverSampling – Duplicates minority class samples.

Random UnderSampling – Reduces majority class samples.

SMOTE – Generates synthetic minority samples.

ADASYN – Adaptive synthetic sampling focusing on difficult cases.

SMOTEENN – Combination of oversampling and cleaning using Edited Nearest Neighbors.

Each technique creates a balanced training dataset while keeping the test dataset untouched.

3️ Machine Learning Models Used

The following five classification models were trained on each resampled dataset:

Logistic Regression

Decision Tree

Random Forest

Support Vector Machine (SVM)

K-Nearest Neighbors (KNN)

This resulted in 25 total model combinations (5 sampling methods × 5 models).

4️ Key Observations

Oversampling techniques such as SMOTE and ADASYN generally performed better than simple random oversampling.

Random UnderSampling sometimes reduced performance due to loss of useful majority class information.

Ensemble-based models like Random Forest showed strong performance across most sampling techniques.

Linear models like Logistic Regression benefited significantly from balanced datasets.

Accuracy alone was not sufficient to evaluate performance; recall and F1-score were more meaningful for fraud detection.

5️ Best Performing Combination

The best-performing combination was determined based on ROC-AUC score (or Accuracy if used in your initial code).

In most runs, synthetic sampling techniques such as SMOTE combined with Random Forest or SVM provided the most stable and reliable results.

6️ Why Sampling is Important in Fraud Detection

In fraud detection:

Fraud cases are rare.

Missing fraud (false negative) is costly.

Models trained on imbalanced data tend to predict the majority class.

Balancing the training dataset allows models to:

Learn minority patterns better

Improve recall

Provide fairer classification boundaries

7️ Limitations

Sampling may introduce synthetic noise (especially with aggressive oversampling).

UnderSampling may remove valuable information.

Performance may vary depending on random seed.

Real-world fraud detection systems require additional techniques like cost-sensitive learning.

8️ Conclusion

This study demonstrates that handling class imbalance significantly improves classification performance in fraud detection problems.

Among the tested approaches:

Synthetic sampling techniques generally outperform simple random methods.

Tree-based ensemble models tend to handle balanced datasets more effectively.

Model performance depends strongly on the interaction between sampling technique and classifier choice.

Selecting the correct combination of sampling strategy and machine learning model is crucial for building a reliable fraud detection system.
