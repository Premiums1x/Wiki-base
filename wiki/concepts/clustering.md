---
concept: clustering
entity_type: technique
aliases: ["聚类"]
sources: ["raw\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-23T06:33:06Z
---

## Definition
Clustering is a task in unsupervised machine-learning, wikilink where the main goal is to group a set of objects in such a way that objects in the same group (called a cluster) are more similar (in some sense or another) to each other than to those in other groups. Clustering builds on the concept of unsupervised learning, wikilink which does not require labeled training data. The primary aim is to discover the inherent grouping in a dataset.

## How it works
The fundamental idea behind clustering is to identify groups within data such that the study of these groups reveals important information. Typically, the similarity of objects is characterized by a distance measure, often the Euclidean distance.

One of the most popular clustering algorithms is K-Means, which aims to partition n observations into k clusters in which each observation belongs to the cluster with the nearest mean. The algorithm works this way:

1. **Initialization**: Randomly select k points as the initial cluster centroids.
2. **Assignment**: Assign each data instance to the cluster with the nearest centroid.
3. **Update**: Calculate the new centroids of each cluster based on mean values of the instances assigned to that cluster.
4. **Repeat**: Repeat the assignment and update steps until the centroids do not change significantly or a certain convergence criterion is met.

Several other clustering methods exist, each with different approaches to similarity measures and updating strategies. For example, Hierarchical clustering builds a tree of clusters, where relationships between the clusters can be represented as a dendrogram. DBSCAN, another method, does not require specifying the number of clusters, instead it uses a distance measure to find dense regions of points.

## Variants
Different clustering methods implement and optimize clustering strategies in varying ways. Techniques vary based on whether the number of clusters is known or unknown, the density and shape of clusters, and the presence or absence of noise and outliers.

- **K-Means**: Simple and widely used, but it assumes clusters to be convex and spherical in shape with equal density. The method is fast and scales well with data size but is sensitive to initialization and can lead to different clusterings if run multiple times.
- **DBSCAN**: Does not require specifying the number of clusters a priori; it is robust to noise and can find arbitrarily shaped clusters.
- **Hierarchical Clustering**: Produces a tree of clusters which can either be agglomerative (bottom-up) or divisive (top-down).

## Trade-offs
Clustering comes with several trade-offs related to the properties of datasets and the specific algorithms used. A significant trade-off involves the choice between the number of clusters (k) and the quality of the clustering. Clustering algorithms that require the number of clusters to be specified make this choice a crucial part of the process and may not always result in the optimal clustering if k is not chosen properly. On the other hand, spectral clustering, which uses techniques in graph theory to partition data into k clusters, depends on the eigenvalues of a Laplacian matrix of the input data. 

Algorithms like K-Means also trade off flexibility for computational simplicity and speed, leading to potential loss of accuracy in complex datasets with non-spherical clusters. Clustering is often unsupervised, requiring careful evaluation to ensure the quality and relevance of the clusters, hence it often depends on the interpretability and domain knowledge of the clusters formed.