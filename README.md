# Naive-Bayes-Classifier
# Naive Bayes Classifier for Enjoy Sports and Iris Datasets

This project involves implementing a Naive Bayes classifier to classify data in the **Enjoy Sports** and **Iris** datasets. The classifier's performance is evaluated by computing metrics such as accuracy, error rate, precision, recall, F1 score, and generating a confusion matrix for visualization.

---

### Table of Contents
1. [Introduction to Naive Bayes Classifier](#introduction)
2. [Advantages of Naive Bayes Classifier](#advantages)
3. [Disadvantages of Naive Bayes Classifier](#disadvantages)
4. [Algorithm](#algorithm)
5. [Formulas Used](#formulas-used)

---

### 1. Introduction to Naive Bayes Classifier
The **Naive Bayes Classifier** is a probabilistic machine learning model based on Bayes’ theorem. It assumes independence between features, meaning each feature contributes independently to the probability of a class label. Naive Bayes is commonly used for classification tasks, especially with categorical data, and is known for its simplicity and computational efficiency.

### 2. Advantages of Naive Bayes Classifier
- **Simple and Fast**: Naive Bayes is easy to implement and computationally efficient.
- **Works Well with Small Data**: It performs well even with a small amount of data and handles missing data effectively.
- **Effective for Categorical Data**: Especially useful in text classification, such as spam detection.
- **Handles Multiple Classes**: Naive Bayes can classify data into multiple classes, making it versatile.

### 3. Disadvantages of Naive Bayes Classifier
- **Independence Assumption**: The classifier assumes that features are independent, which may not hold in real-world data, potentially impacting accuracy.
- **Limited for Continuous Data**: While it can handle continuous data using Gaussian assumptions, it may not perform as well as other algorithms without additional preprocessing.
- **Zero Probability Issue**: If a category has zero frequency in the training data, it assigns zero probability to new instances, which requires techniques like Laplace smoothing to address.

### 4. Algorithm
Here’s a concise algorithm for implementing a Naive Bayes classifier on the Enjoy Sports and Iris datasets:

1. **Load and Preprocess Data**:
   - For the Enjoy Sports dataset: Encode categorical features as numeric values.
   - For the Iris dataset: Ensure the data is numeric and ready for Gaussian calculations.

2. **Split Data**:
   - Divide data into **training** and **testing** sets.

3. **Train the Model**:
   - **Calculate Prior Probabilities** for each class:
     \[
     P(C) = \frac{\text{Number of samples in class } C}{\text{Total samples}}
     \]
   - **Estimate Likelihoods**:
     - For categorical features (Enjoy Sports): Use frequency counts.
     - For continuous features (Iris): Assume Gaussian distribution and calculate mean (\(\mu\)) and variance (\(\sigma^2\)) for each feature in each class.

4. **Make Predictions**:
   - For each test sample, calculate the **posterior probability** for each class:
     \[
     P(C|X) = \frac{P(X|C) \times P(C)}{P(X)}
     \]
   - Assign the class with the **highest posterior probability**.

5. **Evaluate Performance**:
   - **Confusion Matrix**: Compare predictions with actual labels to analyze performance.
   - **Performance Metrics**:
     - **Accuracy**: Measures the proportion of correctly classified instances.
     - **Error Rate**: Calculates the misclassification rate.
     - **Precision and Recall**: Measures the classifier’s performance for each class.
     - **F1 Score**: Balances precision and recall.

### 5. Formulas Used

- **Prior Probability**:
  \[
  P(C) = \frac{\text{Count of class } C}{\text{Total count of all classes}}
  \]

- **Gaussian Likelihood (for continuous data)**:
  \[
  P(X|C) = \frac{1}{\sqrt{2 \pi \sigma^2}} e^{-\frac{(X - \mu)^2}{2 \sigma^2}}
  \]
  where \(\mu\) is the mean and \(\sigma^2\) is the variance for a feature within a class.

- **Posterior Probability**:
  \[
  P(C|X) = \frac{P(X|C) \times P(C)}{P(X)}
  \]

- **Evaluation Metrics**:
  - **Accuracy**:
    \[
    \text{Accuracy} = \frac{\text{TP + TN}}{\text{TP + FP + FN + TN}}
    \]
  - **Error Rate**:
    \[
    \text{Error Rate} = 1 - \text{Accuracy}
    \]
  - **Precision**:
    \[
    \text{Precision} = \frac{\text{TP}}{\text{TP + FP}}
    \]
  - **Recall**:
    \[
    \text{Recall} = \frac{\text{TP}}{\text{TP + FN}}
    \]
  - **F1 Score**:
    \[
    F1 = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}
    \]
