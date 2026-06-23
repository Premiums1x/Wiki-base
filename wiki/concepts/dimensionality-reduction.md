---
concept: dimensionality-reduction
entity_type: technique
aliases: ["降维"]
sources: ["raw\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-23T06:33:16Z
---

## Dimensionality Reduction

### Definition
Dimensionality reduction is a process in machine learning that aims to reduce the number of random variables under consideration, by obtaining a set of principal variables. It [[unsupervised-learning]]-based dim-reduction techniques seek to maintain the relevant information contained in the data while reducing the complexity of the data, which can aid in the visualization of complex data sets and speed up learning algorithms. Dimensionality reduction can be achieved through both linear and nonlinear methods such as pca, t-SNE, and autoencoders.

### How it works
Dimensionality reduction techniques can be broadly classified into two categories: linear and nonlinear.

Linear methods like Principal Component Analysis (PCA) work by transforming the original data into a new coordinate system where the axes are aligned with the directions of maximum variance. In PCA, the algorithm first computes the covariance matrix of the data and then calculates the eigenvectors and corresponding eigenvalues. The eigenvectors with the highest eigenvalues represent the directions that maximize variance in the data. PCA dim-reduction-based approaches then project the original data onto a new set of axes defined by these eigenvectors, effectively reducing the number of dimensions while preserving as much variance as possible.

Nonlinear methods, on the other hand, are capable of handling data that is not linearly separable. t-Distributed Stochastic Neighbor Embedding (t-SNE) is a popular nonlinear technique that aims to preserve the local structure of the data in a low-dimensional space. It achieves this by converting the high-dimensional Euclidean distances into probabilities and then trying to minimize the Kullback-Leibler divergence between the joint probabilities of the high-dimensional and low-dimensional data points.

Autoencoders are neural network models used for encoding and decoding data. They consist of an encoder that maps the input data into a lower-dimensional latent space and a decoder that reconstructs the input from the latent space. The autoencoder is trained to minimize the reconstruction error, which leads to a compressed representation of the input data that captures its most salient features.

### Variants
There are several variants of dimensionality reduction techniques, each with their specific strengths and use cases. Beyond PCA and t-SNE, other notable methods include:

- **Linear Discriminant Analysis (LDA)**: An extension of PCA that seeks to maximize the separation between different classes, especially useful for classification tasks.
- **Independent Component Analysis (ICA)**: An alternative to PCA designed to separate mixed signals into independent components.
- **Autoencoder Variants**: Variants such as Denoising Autoencoders which add noise to the input data to improve robustness, and Variational Autoencoders which model the latent space as a probabilistic distribution.

### Trade-offs
Dimensionality reduction techniques often trade off computational efficiency and simplicity for the quality of the reduced representation. Linear techniques like PCA are faster and easier to compute but may fail to capture the more complex nonlinear relationships in the data. Nonlinear methods like t-SNE can better represent the complex local structure of data but are computationally more expensive and harder to interpret. Furthermore, the choice of dimensionality reduction method often depends on the specific requirements of the task at hand, such as the need for visualization versus maintaining predictive accuracy.