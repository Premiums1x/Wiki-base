---
concept: dimensionality-reduction
entity_type: concept
aliases: []
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T09:45:48Z
---

## Definition
Dimensionality Reduction refers to the process of reducing the number of random variables under consideration, while attempting to retain important information. It is a key technique in machine learning, particularly in scenarios where the original number of dimensions (or features) of the data is high. On one hand, this technique helps simplify the data for easier visualization and interpretation, wikilink data-visualization. On the other hand, it helps improve the performance of machine learning models by reducing overfitting and computational costs. This process wikilink [[unsupervised-learning]] can be either supervised or unsupervised, depending on the availability of labeled data.

## How it works
The core idea behind dimensionality reduction is to transform the original data into lower-dimensional space, where the new features are indicators of the original high-dimensional data. The most common algorithms for dimensionality reduction are Principal Component Analysis (PCA) and t-Distributed Stochastic Neighbor Embedding (t-SNE).

- **PCA**: PCA is a statistical procedure that uses an orthogonal transformation to convert a set of observations of possibly correlated variables into a set of values of linearly uncorrelated variables called principal components. wikilink [[unsupervised-learning]] This method builds on the idea of finding a set of eigenvectors corresponding to the largest eigenvalues in the covariance matrix of the data, effectively projecting the data onto a lower-dimensional space while retaining the maximum variance in the data.

- **t-SNE**: Unlike PCA, t-SNE is particularly well-suited for visualizing high-dimensional datasets in two or three dimensions. It models each high-dimensional observation as a two or three-dimensional point in such a way that observations which are similar in the high-dimensional space will be close in the low-dimensional map, wikilink data-visualization while dissimilar observations remain far apart. Importantly, t-SNE does not attempt to preserve the global structure of the data, but focuses on preserving the local structure.

In both cases, the dimensionality reduction process depends on identifying the underlying structure of the data that explains the most variance or similarity in the data points.

## Variants
There are various other techniques and approaches to dimensionality reduction:

- **Linear Discriminant Analysis (LDA)**: LDA is an efficient technique used to find a linear combination of features that separates two or more classes of objects or events. It maximizes the separation between the means of the classes while minimizing the variance within each class.

- **Autoencoders**: These are a type of artificial neural network used for unsupervised learning of efficient codings. An autoencoder consists of two nets: an encoder network that maps input data to a latent space and a decoder network that maps the latent space back to the original data space. By training the network to minimize the reconstruction error, the autoencoder constrains the latent space to include only the important features of the data.

- **Non-negative Matrix Factorization (NMF)**: NMF is a method that factors a non-negative matrix into a product of two non-negative matrices, where one of them is often a dictionary of basis elements. NMF has applications in fields such as text mining, where the matrix being decomposed represents the document-term matrix of a corpus, and in computer vision, where it can be used for dimensionality reduction and feature extraction.

- **Covariance Matrix Adaptation Evolution Strategy (CMA-ES)**: Though primarily known as an evolutionary strategy optimization method, CMA-ES can also be adapted for dimensionality reduction when applied to problems where the covariance matrix can be adapted to reflect the structure of the data.

## Trade-offs
Dimensionality reduction comes with its own trade-offs that must be carefully considered:

- **Loss of Information**: While dimensionality reduction manages to improve the performance and interpretability of a model, it comes at the cost of losing some information. Information that is not captured by the principal components or other reduced dimensions can be crucial for the decision-making process.

- **Choice of Algorithm**: Different algorithms have different characteristics. PCA is a linear method that works well with linear features but might underperform when dealing with non-linear data. t-SNE, on the other hand, is better suited for capturing the non-linear structure of data but does not always provide interpretable results for all scenarios.

- **Computation Cost**: Algorithms such as t-SNE can be very computationally expensive, especially with large datasets. PCA and other linear methods offer a trade-off between computational cost and dimensionality reduction efficiency.

- **Overfitting**: Reducing the dimensions of data too much may result in overfitting the dataset, where the model captures noise and outliers in place of the true signal. It is important to select the right number of dimensions to keep to balance the reduction of overfitting and the preservation of information.

## See also
- data-visualization
- [[unsupervised-learning]]