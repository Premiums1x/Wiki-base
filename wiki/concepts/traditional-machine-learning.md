---
concept: traditional-machine-learning
entity_type: concept
aliases: ["传统机器学习"]
sources: ["raw\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-23T06:32:43Z
---

## Definition
Traditional Machine Learning (Traditional ML) is a branch of [[artificial-intelligence]] that uses statistical algorithms and computational methods to enable machines to "learn" from data without being explicitly programmed. Unlike [[deep-learning]], traditional ML techniques primarily work with structured data and rely on mathematical models for inference and prediction.

## How it works
Traditional ML operates on a well-defined and categorized dataset, where the data can be labeled or unlabeled.

### Supervised Learning
In supervised learning, the model is trained on a dataset with known outcomes or labels label. The goal is to learn a function that maps inputs to outputs accurately. Common supervised learning tasks include [[classification]] and [[regression]]:

- **Classification** aims to predict discrete categories or classes, such as distinguishing spam emails from non-spam emails. Algorithms used for classification include Support Vector Machines (SVM), Decision Trees, and Random Forests.
- **Regression** involves predicting a continuous value, like predicting house prices. Linear Regression is a typical algorithm for regression problems.

### Unsupervised Learning
Unsupervised learning algorithms work with data where the outcomes are unknown at the time of training. These algorithms aim to uncover hidden patterns or intrinsic structures from the data:

- **Clustering** involves grouping a set of objects in such a way that objects in the same group (called a cluster) are more similar to each other than to those in other groups. K-Means is a popular algorithm for clustering.
- **Dimensionality Reduction** reduces the number of random variables under consideration by obtaining a set of principal variables. Principal Component Analysis (PCA) is a widely used technique for reducing dimensionality.

### Relationship to Deep Learning
Traditional ML extends the concept of using mathematical models to analyze structured data. In contrast, [[deep-learning]] builds on the principles of artificial neural networks, particularly those with multiple layers, to handle more complex and unstructured data such as images and text.

## Variants
The key variants of traditional machine learning include supervised and unsupervised learning, with specific algorithms like SVMs, Decision Trees, Random Forests, Linear Regression, K-Means, and PCA. These variants are optimized for different use cases and data types.

## Trade-offs
The trade-offs of traditional ML include its reliance on feature engineering, which feature-engineering is a prerequisite of traditional machine learning but can be labor-intensive and requires domain expertise. Moreover, traditional ML methods may be less effective on large and complex datasets compared to deep learning techniques, which trade computational complexity for improved performance on such datasets.

## See also
- feature-engineering
- [[supervised-learning]]
- [[unsupervised-learning]]
- [[classification]]
- [[regression]]
- [[clustering]]
- [[dimensionality-reduction]]
- [[deep-learning]]