# Results Summary

This section summarizes the performance of the four machine learning models used for password strength classification: MultiLayer Perceptron (MLP), MLPClassifier, Gaussian Naive Bayes, and Logistic Regression.

## Confusion Matrix Analysis

![confusion_matrix_comparison](https://github.com/user-attachments/assets/341bfe15-ff5d-49c9-85c7-50dcb8921f6b)

The confusion matrices showed:

- **Logistic Regression** and **MLPClassifier** achieved very high classification accuracy with minimal misclassifications.
- **MLP** showed slightly more noise, particularly around Class 1 predictions.
- **Gaussian Naive Bayes** performed poorly with a high number of incorrect classifications across classes.

## Absolute Error Map Analysis

![absolute_error_comparison](https://github.com/user-attachments/assets/209bd223-78e5-49a1-96e7-8526d6cdfe3f)

An absolute error heatmap was generated for each model:

- **Gaussian Naive Bayes** exhibited extremely large errors (up to ~100,000 misclassifications), particularly confusing Class 0 → 1 and Class 1 → 2.
- **Logistic Regression**, **MLP**, and **MLPClassifier** maintained low error counts (<150 misclassifications between classes), with errors mostly localized near class boundaries.

## Individual Model Performance

### MultiLayer Perceptron (MLP)
- Very slightly more errors for Class 1 compared to MLPClassifier and Logistic Regression.
- Demonstrated strong generalization but introduced minor noise due to learning non-linearities.

### MLP Classifier
- Very few errors, similar to Logistic Regression.
- Less than 150 misclassifications between classes.
- Slightly better performance than basic MLP, particularly at cleanly separating classes.

### Gaussian Naive Bayes
- Huge absolute errors, with approximately 100,000+ misclassifications across all classes.
- Poor separation between adjacent classes (especially Class 0 → 1 and Class 1 → 2).
- Assumptions of feature independence and Gaussian distribution were violated in the dataset, contributing to poor performance.

### Logistic Regression
- Very few errors, comparable to MLPClassifier.
- Less than 150 misclassifications, mainly between Class 0 → 1.
- Modeled the decision boundary very effectively, fitting the problem structure well.

## Post-Analysis: Investigating Suspiciously High Accuracy

After achieving extremely high classification results (over 99.9% accuracy in three models), a deeper investigation was performed to ensure validity:

- **Suspiciously Accurate Results**  
  Three models achieved over 99.9% accuracy, which triggered a review of potential data issues.

- **Class Imbalance**  
  The dataset exhibited a heavy skew, with approximately 75% of passwords classified at strength level 1 (Medium).
  - This imbalance allowed models to achieve high overall accuracy by primarily predicting the majority class.

- **Dataset Source Bias**  
  The password strength labels were based on the PARS tool, which applied commercial password meter heuristics.

- **Overlapping Features**  
  Features used in training (e.g., password length, composition) directly overlapped with the scoring rules used by password meters.
  - As a result, models essentially replicated known heuristics rather than discovering deeper or independent patterns.

These findings suggest that while model accuracy was very high, it was partially inflated by the structure and bias present in the dataset.

## Dataset Source

Original dataset:  
[Password Strength Classifier Dataset - Kaggle](https://www.kaggle.com/datasets/bhavikbb/password-strength-classifier-dataset)
