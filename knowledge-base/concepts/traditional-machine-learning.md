---
concept: traditional-machine-learning
entity_type: concept
aliases: []
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T07:59:54Z
---

## Definition
Traditional Machine Learning refers to a set of techniques that employ mathematical and statistical methods to process structured data. These techniques allow computers to "learn" from past data without explicit programming, forming the foundation of modern machine learning ai-and-machine-learning. Traditional Machine Learning builds on the basic principles of computer science and mathematics, specifically focusing on supervised and unsupervised learning methods [[supervised-learning], [unsupervised-learning]].

## How it Works
The basic principle of traditional machine learning involves developing algorithms that can make predictions or decisions using data-specific rules. This process can be broken down into several steps:
1. Data is collected and cleaned, often in structured formats such as tables.
2. Features are extracted or selected to describe the elements in the dataset.
3. An appropriate algorithm is chosen based on the problem type and data structure.
4. The algorithm is trained on a portion of the data, called the training set.
5. The performance of the algorithm is evaluated on a separate portion of the data, known as the validation or testing set.

For supervised learning, the algorithm learns a mapping from inputs to outputs using labeled data. Common tasks include classification, where the goal is to predict a discrete class label, and regression, where the aim is to predict numerical values based on existing data [[regression]].

In contrast, unsupervised learning deals with unlabeled data, aiming to discover hidden structures within the data itself. Key unsupervised learning tasks include clustering, where similar data points are grouped together, and dimensionality reduction, which aims to reduce the number of random variables under consideration.

Traditional machine learning techniques play a crucial role in understanding and implementing modern AI models, providing the foundational knowledge required for developing more complex algorithms like deep learning [[deep-learning]]. Techniques from traditional machine learning are prerequisites for understanding the architectural decisions made in deep learning models, particularly in feature extraction and understanding which features are most pertinent for a given task.

## Variants
Traditional machine learning encompasses a range of variants and specific implementations that can be categorized based on their architecture and methods. Different algorithms are designed to handle distinct types of problems:
- **Classification**: Algorithms such as decision trees decision-trees, random forests, and support vector machines svm are used.
- **Regression**: Techniques including linear regression and polynomial regression are often applied.
- **Clustering**: K-means is a popular algorithm for clustering.
- **Dimensionality Reduction**: Principal Component Analysis (PCA) is commonly used for this purpose.

These methods extend the basic principles of learning from data to specific, more refined tasks. Each algorithm is implemented with different strengths and weaknesses for handling various data types and structures. For instance, while decision trees are easy to interpret and can handle both numerical and categorical data, they are prone to overfitting. Support vector machines, on the other hand, are effective in high-dimensional spaces but can be less effective in large datasets with lots of features.

## Trade-offs
Traditional machine learning models come with several trade-offs:
- **Feature Engineering Dependence**: Many traditional models heavily rely on handcrafted features, which can be expensive and time-consuming to develop.
- **Scalability**: Scaling traditional models to big data challenges can be difficult, often limited by computational resources and model complexity.
- **Interpretability vs. Performance**: Models like decision trees and logistic regression are easier to understand but might not achieve the highest performance compared to complex models.

These techniques also depend on extensive domain knowledge and empirical adjustments to reach optimal performance, indicating that they require a significant investment in human expertise.

## See also
[[regression]], [[supervised-learning]], unsupervised-learning, svm, decision-trees