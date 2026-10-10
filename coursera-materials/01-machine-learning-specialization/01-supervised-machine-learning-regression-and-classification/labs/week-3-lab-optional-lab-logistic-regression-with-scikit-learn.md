---
type: lab
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 3
section: Gradient descent for logistic regression
item_title: Optional lab: Logistic regression with scikit-learn
source_url: https://www.coursera.org/learn/machine-learning/ungradedLab/F3ZpI/optional-lab-logistic-regression-with-scikit-learn
notebook_path: C1_W3_Lab07_Scikit_Learn_Soln.ipynb
language: en
extracted_at: 2026-10-09T17:16:29+08:00
status: success
---
# Optional lab: Logistic regression with scikit-learn

# Ungraded Lab:  Logistic Regression using Scikit-Learn

## Goals
In this lab you will:
-  Train a logistic regression model using scikit-learn.

## Dataset 
Let's start with the same dataset as before.

```python
import numpy as np

X = np.array([[0.5, 1.5], [1,1], [1.5, 0.5], [3, 0.5], [2, 2], [1, 2.5]])
y = np.array([0, 0, 0, 1, 1, 1])
```

## Fit the model

The code below imports the [logistic regression model](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html#sklearn.linear_model.LogisticRegression) from scikit-learn. You can fit this model on the training data by calling `fit` function.

```python
from sklearn.linear_model import LogisticRegression

lr_model = LogisticRegression()
lr_model.fit(X, y)
```

## Make Predictions

You can see the predictions made by this model by calling the `predict` function.

```python
y_pred = lr_model.predict(X)

print("Prediction on training set:", y_pred)
```

## Calculate accuracy

You can calculate this accuracy of this model by calling the `score` function.

```python
print("Accuracy on training set:", lr_model.score(X, y))
```

