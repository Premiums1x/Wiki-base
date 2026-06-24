---
concept: regression
entity_type: concept
aliases: []
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T08:00:08Z
---

## Definition
Regression is a statistical method used in [[machine-learning]] to estimate the relationships among variables. Specifically, it predicts the value of a continuous target variable based on one or more predictor variables. Regression analysis helps in understanding how the typical value of the dependent variable changes when any one of the independent variables is varied, while the other independent variables are held fixed.

## How it works
In the context of machine learning, regression supervised-learning|extends supervised learning by focusing on predicting a continuous output variable. It requires a dataset where each data point includes a set of features and a target value, with labels indicating the continuous values the algorithm aims to predict.

The core mechanism of regression involves building a model that fits the data. Linear regression, a simple model in regression, assumes a linear relationship between the inputs and outputs. The algorithm minimizes a loss function, typically mean squared error (MSE), to find the optimal parameters for predicting the target variable. Beyond linear models, more complex forms like polynomial regression or regression trees are available, which can handle more complex data relationships.

## Variants
Several types of regression algorithms exist, each implementing the core principle in different ways based on the underlying data complexity and structure:
- **Linear Regression**: Used for simple linear relationships, it assumes that there’s a linear relationship between the predictor and the response variable.
- **Polynomial Regression**: This extends linear regression by adding higher degree terms to the equation, allowing for more complex models.
- **Logistic Regression**: Despite its name, logistic regression is used for classification problems when the target variable is binary, rather than continuous.
- **Ridge Regression** and **Lasso Regression**: These are variants that implement regularization to avoid overfitting by penalizing large coefficients.

## Trade-offs
Regression methods have several trade-offs:
- **Linearity and Simplicity**: Linear regression is highly effective when data is linear, but it may trades-off poor performance when the data has a more complex relationship that's not linear.
- **Interpretability vs. Complexity**: Simpler models like linear regression are easier to interpret but might not capture complex patterns as well as more complex models, such as decision trees or neural networks.
- **Overfitting**: Especially in polynomial regression, models can overfit the training data if the polynomial degree is too high, leading to poor generalization on unseen data.
- **Feature Dependencies**: Some types of regression require the features to be independent, which may not always be the case in real-world data.

## See also
- [[supervised-learning]]
- unsupervised-learning
- [[classification]]
- [[deep-learning]]