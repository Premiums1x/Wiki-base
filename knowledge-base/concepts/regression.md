---
concept: regression
entity_type: concept
aliases: []
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T09:45:17Z
---

## Definition
Regression is a statistical method and a central task in machine-learning|machine learning, particularly in supervised-learning|supervised learning, where it is used to predict a continuous outcome based on one or more predictors or explanatory variables. Essentially, regression helps understand and predict the relationship between variables by estimating the average value of the dependent variable for fixed values of the independent variables. In practice, regression models aim to find a function that best fits the data, such that the differences between the observed data and the predicted values are minimized.

## How it works
In traditional machine learning, regression models build on the concept of statistical-analysis|statistical analysis to predict continuous outputs by training on labeled data. This process involves collecting a dataset of input-output pairs, where the outputs are the continuous numerical values we seek to predict based on the inputs. The algorithm then learns the parameters of a function that maps inputs to outputs, designed to minimize some form of error criterion, such as mean-squared-error|mean squared error (MSE). When this function is well-learned from the training data, it can be used to make predictions on new input data points, which leads to an estimate of the corresponding output.

There are various types of regression methods, each making different assumptions about the distribution of the data and the nature of the relationship between the predictors and the response variables. Common regression techniques include:
- **Linear Regression** (Simple and Multiple): A linear approach to modeling the relationship between a scalar dependent variable and one or more explanatory variables.
- **Polynomial Regression**: A form of regression analysis in which the relationship between the independent variable x and the dependent variable y is modeled as an nth degree polynomial in x.
- **Logistic Regression**: Despite its name, it is a classification technique, where the output is categorical. However, it can be viewed as a regression problem where the outcome is limited to a binary response, thus it can be linked to regression through a transformation.
- **Ridge Regression** and **Lasso Regression**: These extensions to linear regression include a regularization term in the loss function, which helps in shrinking the coefficients towards zero to avoid overfitting.

Each regression type can further extend the model to accommodate interactions and nonlinearities, optimizing the prediction accuracy through various optimization techniques that depend on the specific formulation of the regression problem.

## Variants
The key variants of regression are primarily defined by the different forms of the regression equation and the assumptions made about the residuals. These are either:
- **Parametric Regression**: Assumes a known form for the regression equation, such as linear or polynomial. This includes linear-regression|linear regression, which is built on the basics of linear algebra.
- **Non-parametric Regression**: Does not assume a specific form for the regression equation. Techniques such as **Local Regression** (LOESS) and **Hierarchical Regression** can be considered when the relationship between the dependent and independent variables is complex and not easily described by parametric forms.
- **Regularized Regression**: Introduces a penalty term to the loss function to penalize the complexity of the model, reducing the chances of overfitting. ridge-regression|Ridge Regression and lasso-regression|Lasso Regression fall into this category and can be seen as optimizations of basic regression techniques like linear regression.

## Trade-offs
The trade-offs in using regression methods involve a balance between model complexity and prediction accuracy. Depending on the nature of the data and the assumptions made about the underlying relationships, simpler models such as simple linear regression may perform adequately while more complex models might offer better predictive accuracy but are often more prone to overfitting and require more data and computational resources. The choice of regression type heavily depends on the specifics of the problem at hand, including the presence of outliers, the size of the dataset, the need for interpretability, and the amount of available data. For high-dimensional data, regularized-regression|regularized regression methods are often preferred due to their ability to introduce necessary penalties and biases that prevent overfitting, while still capturing the underlying trends in the data.