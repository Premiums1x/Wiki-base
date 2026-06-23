---
concept: unsupervised-learning
entity_type: technique
aliases: ["无监督学习"]
sources: ["raw\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-23T06:32:59Z
---

## Definition
Unsupervised Learning is a branch of machine learning where algorithms are used to analyze and classify unlabeled datasets. Unlike [[supervised-learning]], which relies on labeled data to train models, unsupervised learning identifies an inherent structure of the input data in order to organize or describe it in a useful way. It builds on the concept of data analysis and pattern recognition to uncover hidden patterns and relationships in data without the guidance of labels.

Since unsupervised learning does not rely on a predefined set of labels, the learning tasks primarily focus on clustering and dimensionality reduction, where the algorithm forms clusters within the data based on similarities and reduces the number of input variables while retaining important properties.

## How it works
In unsupervised learning, algorithms seek out natural groupings in the dataset or find a lower-dimensional representation of the data. The process usually involves several steps:
1. Data preparation: Input data is preprocessed to ensure consistency and quality.
2. Algorithm application: The algorithm is applied to the data, often seeking to reveal hidden patterns or forms of structure.
3. Model evaluation: The results are evaluated to ensure they accurately capture the important structures within the data. Evaluation is crucial because there are no predefined labels by which to measure accuracy.

- Clustering: This is a type of unsupervised learning that involves partitioning of a dataset into a set of "subgroups" or clusters. Objects within the same cluster are more similar to each other based on predefined similarity metrics than to objects in other clusters. K-means is a common algorithm used for clustering.
- Dimensionality Reduction: This process reduces the number of random variables under consideration by obtaining a set of principal variables. Techniques like PCA (Principal Component Analysis) are used to transform the dataset into a lower-dimensional space that captures the most significant features of the data. This is particularly useful for visualization and to reduce computational complexity.

Each step in unsupervised learning builds on statistical and analytical methods to understand the structure inherent within the data, without relying on labeled outputs.

## Variants
Several variants of unsupervised learning techniques exist, each tailored to specific types of data and problems:
- **K-Means Clustering**: A method of clustering where the algorithm groups data objects into a predefined number of clusters to minimize the within-cluster variance. This method is an implementation of clustering algorithms.
- **Hierarchical Clustering**: Forms a tree of clusters where each node is a cluster with its children being sub-clusters. This technique is particularly useful when the data is hierarchical in nature.
- **Self-Organizing Maps (SOM)**: A type of artificial neural network that is trained using unsupervised learning to produce a low-dimensional (typically two-dimensional) representation of the input space of the training samples, referred to as a map.
- **DBSCAN (Density-Based Spatial Clustering of Applications with Noise)**: An algorithm that is particularly effective for clustering data of varying density. DBSCAN groups together points that are packed closely together (points with many nearby neighbors), marking as outliers points that lie alone in low-density regions (whose nearest neighbors are too far away).
- **Principal Component Analysis (PCA)**: A statistical method that transforms a set of possibly correlated variables into a smaller number of uncorrelated variables called principal components. PCA is a widely used technique for dimensionality reduction.

Each of these techniques has its own strengths and weaknesses which make them suitable for different types of data sets and clusters.

## Trade-offs
Unsupervised learning methods, while powerful for understanding large, complex datasets without labels, have several trade-offs and limitations:
- Interpreting results: Because the output of an unsupervised learning model is not compared against a label, understanding what the model is finding can often be difficult. This contrasts with the clarity provided by methods in supervised learning.
- Dependency on parameter tuning: Many unsupervised algorithms depend heavily on the choice of parameters, such as the number of clusters in K-Means. Without specific criteria for optimization, these parameters can lead to widely varying outcomes.
- Sensitivity to input scale: Unsupervised techniques can be sensitive to the scale of different features within the input data, requiring proper feature scaling to achieve good performance.
- Limited use of prior knowledge: Unlike supervised learning, which explicitly uses labeled data to train models, unsupervised learning lacks the structured guidance that can be provided by domain-specific knowledge, which can be a drawback in certain applications.

Unsupervised methods often rely on complex and abstract reasoning about the data structure, which can make them less intuitive and more prone to errors than supervised approaches.

## See also
- [[supervised-learning]]
- [[clustering]]