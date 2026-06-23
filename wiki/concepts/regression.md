---
concept: regression
entity_type: technique
aliases: ["回归"]
sources: ["raw\\ai_machine_learning.md"]
confidence: medium
created_at: 2026-06-23T06:33:05Z
---

## Definition
Regression is a type of [[supervised-learning]] task in [[machine-learning]], where the model is trained to predict a continuous outcome variable, or target, based on one or more input variables, referred to as features or predictors. [[classification]] is the counterpart of regression, where the target variable is categorical instead of continuous. Regression extends and builds on the principles of statistical modeling, enabling more nuanced predictions applicable to real-world scenarios requiring numerical outputs, such as predicting house prices or stock market trends.

## How it works
The process of regression analysis involves modeling the relationship between the input features and the output variable using a dataset where these relationships are known. This relationship is expressed as a mathematical equation, typically a linear one in the simplest regression models, which can approximate the mapping from inputs to outputs. Commonly, regression algorithms estimate the coefficients of this equation during the training phase, which minimize the difference between the predicted values and the actual values in the training dataset.

For instance, in the case of linear-regression, the model fits a straight line through the data points so that the sum of the squared differences between the observed and the predicted values is minimized—a process known as least squares regression. This approach builds on the linear algebra foundations, specifically vector and matrix operations, making it accessible and interpretable. More sophisticated regression techniques, such as polynomial regression, use higher-order equations to fit the data better.

To improve upon linear regression, other variants of regression, such as ridge-regression and lasso-regression, add regularization penalties to the cost function, which can prevent overfitting by discouraging excessively complex models. Each type of regression model implements a different strategy for this fitting process, thus optimizing different aspects of model performance.

### Trade-offs
Trade-offs in regression models include computational cost, interpretability, and predictive accuracy. Linear models are straightforward and computationally efficient but may not capture complex patterns in the data. On the other hand, more complex models, such as non-linear regression techniques, require more computational resources and may suffer from overfitting if not carefully regularized. Additionally, these models can be harder to interpret, making it more challenging to understand how the model is using the input features to make predictions. This trade-off depends on the complexity and requirements of the application, as well as the availability of computational resources.

## Variants
Regression techniques come in various forms, each with its own assumptions and optimizations. Linear regression assumes a linear relationship between features and the target variable and is extendable to more complex models like polynomial regression, which models non-linear relationships through polynomial functions. Logistic regression, despite its name, is a [[classification]] algorithm and does not optimize the same outcomes as regression models but is related in its use of a linear model and the principle of minimizing a cost function.

Other notable regression techniques include:
- **Ridge regression**: Implements linear regression with an added regularization parameter to penalize the magnitude of the coefficients, essentially trading off simplicity for a reduction in variance.
- **Lasso regression**: Also a variant of linear regression that adds a regularization term that can shrink some coefficients to zero, effectively performing feature selection.
- **Elastic Net regression**: Extends Lasso regression by combining both L1 and L2 regularization, balancing the feature selection aspect of Lasso with the stability of Ridge regression.

## Trade-offs
- Linear regression, while computationally efficient and easy to understand, assumes a linear relationship between the independent and dependent variables, which might not always be realistic. This model may also suffer from multicollinearity or overfitting if not regularized correctly.
- Ridge regression avoids overfitting by penalizing large coefficients but does not perform feature selection.
- Lasso regression does perform feature selection but can be unstable when feature collinearity is high.
- Elastic Net regression balances the benefits of both Ridge and Lasso, implementing a compromise between the regularization of L2 and feature selection of L1, but it introduces another parameter which must be tuned, increasing model complexity.

## See also
- [[classification]]
- [[supervised-learning]]