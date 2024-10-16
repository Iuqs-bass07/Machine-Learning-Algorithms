# Support Vector Machine (SVM) from Scratch

This repository contains an implementation of a Support Vector Machine (SVM) from scratch using Python. The SVM algorithm is designed to classify data points by finding the optimal hyperplane that maximizes the margin between two classes. This implementation uses gradient descent to minimize the hinge loss for misclassified points.

## Introduction

SVM is a powerful supervised learning algorithm for classification tasks. It works by finding the optimal hyperplane that separates the data points from different classes with the maximum margin. This implementation provides a simple approach using gradient descent to minimize the hinge loss, which is the loss function used in SVM.

## Theory

### Hyperplane

The SVM algorithm finds a hyperplane that best divides the data points into two classes. The equation of the hyperplane is defined as:

\[
f(x) = \mathbf{w} \cdot \mathbf{x} + b
\]

### Support Vectors

Support vectors are the data points that lie closest to the hyperplane. These points are critical because they define the position and orientation of the hyperplane. The margin is defined as the distance between the hyperplane and the closest support vectors.

### Hinge Loss

SVM uses hinge loss to penalize misclassified points. The hinge loss function is defined as:

\[
\text{Loss} = \max(0, 1 - y_i(\mathbf{w} \cdot \mathbf{x}_i + b))
\]

Where:
- **y_i** is the true label of the point \(x_i\).
- \(\mathbf{w} \cdot \mathbf{x}_i + b\) is the predicted value for the point \(x_i\).

#### Correctly Classified Points
When a point is correctly classified (i.e., lies on the correct side of the hyperplane), the condition holds:

\[
y_i(\mathbf{w} \cdot \mathbf{x}_i + b) \geq 1
\]

In this case, the hinge loss is 0, meaning no penalty is applied.

#### Misclassified Points
When a point is misclassified (i.e., lies on the wrong side or within the margin), the condition holds:

\[
y_i(\mathbf{w} \cdot \mathbf{x}_i + b) < 1
\]

In this case, the hinge loss is greater than 0, and the algorithm updates the weights and bias using gradient descent to reduce this loss.

## Implementation

### Training

The `fit()` function trains the SVM model using the following steps:

1. Initialize the weights (`w`) and bias (`b`).
2. For each training example:
   - Check if the point is correctly classified using the condition:
     \[
     y_i(\mathbf{w} \cdot \mathbf{x}_i + b) \geq 1
     \]
   - If correctly classified, update the weights as:
     \[
     \mathbf{w} \leftarrow \mathbf{w} - \text{learning rate} \times (2 \times \lambda \times \mathbf{w})
     \]
   - If misclassified, update the weights and bias as:
     \[
     \mathbf{w} \leftarrow \mathbf{w} - \text{learning rate} \times (2 \times \lambda \times \mathbf{w} - \mathbf{x}_i \times y_i)
     \]
     \[
     b \leftarrow b - \text{learning rate} \times y_i
     \]

### Prediction

The `predict()` function classifies new data points by computing the decision boundary:

\[
f(x) = \text{sign}(\mathbf{w} \cdot \mathbf{x} + b)
\]

- If \( f(x) > 0 \), the point belongs to the positive class.
- If \( f(x) < 0 \), the point belongs to the negative class.
