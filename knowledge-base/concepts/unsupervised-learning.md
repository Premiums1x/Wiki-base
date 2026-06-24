---
concept: unsupervised-learning
entity_type: concept
aliases: []
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T09:45:27Z
---

## Definition
Unsupervised Learning is a type of machine learning technique where algorithms learn from datasets without the guidance of a human-labeled response or outcome. Unlike [[supervised-learning]], Unsupervised Learning deals with untagged or unlabeled data, aiming to identify hidden structures or patterns within the data data-scientist. It extends the core concept of Machine Learning by addressing problems where data comes without clear target outcomes, thereby enabling the discovery of inherent structures and relationships.

## How it works
Unsupervised Learning helps in understanding the underlying distribution of datasets and forming representations without labeled examples. Algorithms are usually trained on the input data to learn the internal structure and distribution on their own. Two main functions of Unsupervised Learning are [[clustering]] and [[dimensionality-reduction]]. In Clustering, the algorithm groups data points into clusters such that points in the same cluster are more similar to each other than to those in other clusters. This is an implementation of pattern identification within unlabeled data. K-means, a widely used clustering method, builds on partitioning the data into clusters based on the distance between data points. On the other hand, Dimensionality Reduction techniques, such as principal-component-analysis, reduce the number of random variables under consideration, optimizing for both computational speed and model accuracy by lowering the number of input variables. Unsupervised Learning often trades off interpretability for automation. Since the learning process occurs without guidance, there can be less certainty in the results, leading to challenges in understanding the model's internal decision-making process. Despite these challenges, Unsupervised Learning is crucial in exploratory data analysis and finding hidden patterns, which are often prerequisites for supervised learning tasks or further data preparation steps.

## Variants
Unsupervised Learning encompasses several algorithms that are used based on the specific nature of the problem and the structure of the data:

1. **Clustering Algorithms**
   - k-means-clustering: This algorithm is a form of partition-based clustering, implementing the idea of dividing data into several clusters where each observation belongs to the cluster with the nearest mean.
   - hierarchical-clustering: This builds a tree of clusters (referred to as a dendrogram), qualifying as a form of clustering that looks at hierarchical relationships between data.

2. **Dimensionality Reduction Techniques**
   - principal-component-analysis: An optimization technique that transforms the original variables to a new set of variables, ensuring maximum variance of the data is maintained while reducing its dimensionality.
   - t-distributed-stochastic-neighbor-embedding: A visualization technique that is particularly effective in lower-dimensional space, like transforming high-dimensional data into 2D or 3D scatter plots for enhanced visual perception.

## Trade-offs
Unsupervised Learning models inherently trade off accuracy and precision for a broader understanding of data distribution and structures. They require large amounts of unlabeled data to generate any useful information, which contrasts with supervised learning approaches that can utilize smaller, labeled datasets. Additionally, the effectiveness of Unsupervised Learning is highly dependent on the nature and quality of the data. Furthermore, because there are no clear labels to guide the learning process, it is more challenging to evaluate the performance of unsupervised models. To mitigate these issues, Unsupervised Learning often trades off simplicity in algorithm design with increased complexity in understanding the results.

## See also
- [[clustering]]
- [[dimensionality-reduction]]
- principal-component-analysis