---
concept: machine-learning
entity_type: concept
aliases: []
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T07:59:56Z
---

## Definition
Machine Learning (ML) is a key branch of [[artificial-intelligence]] that focuses on enabling computers to learn from data and improve their performance on tasks without being explicitly programmed. ML algorithms can discover patterns in data and make predictions or decisions based on those patterns, extending the reach of traditional software development approaches that rely solely on human-defined rules.

## How it works
The process of ML involves several steps. First, a dataset is gathered and prepared for analysis, often requiring cleaning and preprocessing to ensure quality and consistency. The dataset is split into a training set and a test set; the algorithm is trained on the former and validated on the latter to assess its generalization capability.

### Traditional Machine Learning
Traditional ML methods primarily focus on structured data and rely on mathematical and statistical techniques. They are categorized into two main types:

#### Supervised Learning
Supervised learning algorithms are trained using labeled data, where each input comes paired with a corresponding output label. The goal is to predict the output for a new input based on the learned mapping. Common tasks include classification (like identifying spam emails) using algorithms such as Support Vector Machines (SVMs) and Decision Trees, and regression (predicting continuous values like stock prices) using linear regression.

#### Unsupervised Learning
Unsupervised learning deals with unlabeled data, where the goal is either to find patterns within the data or to reduce its dimensionality without prior knowledge of outcomes. Clustering algorithms like K-Means are used for tasks like customer segmentation, and dimensionality reduction techniques like Principal Component Analysis (PCA) help visualize high-dimensional datasets by reducing their feature space.

### Deep Learning
Deep Learning, a subset of machine learning, builds on the principles of artificial neural networks, particularly those with multiple hidden layers, to process complex information hierarchies directly from raw data. These neural networks, including Convolutional Neural Networks (CNNs) and Recurrent Neural Networks (RNNs), have achieved human-level performance in tasks ranging from image recognition to natural language processing. The Transformer architecture, by introducing the self-attention mechanism, has further optimized the way these networks learn, making them highly effective for processing sequential data and forming the backbone of modern large language models (LLMs).

### Large Language Models (LLMs)
LLMs are sophisticated models that have been pre-trained on vast amounts of text data using Transformer architectures. The pre-training phase typically involves learning general world knowledge and language structure through predicting the next token in a sequence. After pre-training, these models may undergo fine-tuning (SFT) and reinforcement learning with human feedback (RLHF) to adapt to specific tasks or align with human values. Recent advancements also include retrieval-augmented generation (RAG), which integrates external knowledge databases to enhance the context for model responses.

## Variants
There are numerous variants of machine learning techniques, each with its own strengths and use cases. Popular variants include:

- **Convolutional Neural Networks (CNNs)**, which are optimized for processing grid-like data such as images and videos.
- **Recurrent Neural Networks (RNNs) and Long Short-Term Memory (LSTM) networks** are specifically designed to handle sequential data such as text and time series.
- **Transformer models**, which are based on the concept of self-attention, have become a preferred architecture in natural language processing (NLP) due to their ability to capture long-range dependencies.

## Trade-offs
While machine learning offers powerful tools for making sense of data, there are several trade-offs to consider:

- **Interpretability**: The more complex the model, the harder it can be to understand why it makes certain predictions. Deep learning models, in particular, can be seen as black boxes, challenging their explainability, trades off with the need for transparency in decision-making processes.
- **Generalization**: Highly specialized models may excel in narrowly defined tasks but fail to perform well on data that slightly deviates from the training set. This is a common issue in machine learning, where overfitting the data can lead to poor generalization.
- **Scalability**: Training machine learning models, especially deep neural networks, requires substantial computational resources and time. This is a significant barrier to the broader adoption of advanced models, trades off with the resource requirements of training large datasets.

## See also
- natural-language-processing
- data-science
- neural-networks
- big-data
- [[artificial-intelligence]]