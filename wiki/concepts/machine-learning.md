---
concept: machine-learning
entity_type: concept
aliases: ["ml"]
sources: ["raw/ai_machine_learning.md"]
confidence: high
created_at: 2026-06-23T03:36:13Z
---

## Definition

Machine Learning (ML) is a branch of Artificial Intelligence (AI) that focuses on enabling computers to learn from data and improve their performance on specific tasks without explicit programming. This involves developing algorithms that can analyze and draw inferences from data to make decisions or predictions.

## How it works

Machine Learning operates by using statistical models to identify patterns within data sets. Two primary types of learning methods are typically employed:

- **Supervised Learning**: This method uses labeled training data, where each example includes an input and a desired output. The algorithm learns to map the input to the output by adjusting its parameters to minimize error rates. Common tasks include classification (e.g., categorizing emails as spam or not spam) and regression (e.g., predicting housing prices).

- **Unsupervised Learning**: This method employs unlabeled data, and the algorithm must find hidden structures or patterns within the data. Common tasks include clustering (e.g., grouping customers based on purchasing behavior) and dimensionality reduction (transforming multidimensional datasets into a lower-dimensional space).

Machine Learning also involves **Deep Learning**, a subset that uses artificial neural networks with many layers (deep neural networks) to model complex patterns. Techniques such as Convolutional Neural Networks (CNNs) for image processing and Recurrent Neural Networks (RNNs) for sequence data like speech and text processing are integral to deep learning.

## Variants

- **Traditional Machine Learning**: Utilizes mathematical and statistical methods to process structured data. Common algorithms include Support Vector Machines (SVM), Random Forests, and Linear Regression.

- **Deep Learning**: Employs neural networks, particularly those with multiple hidden layers (deep neural networks). Techniques include CNNs for image analysis, RNNs for sequence data, and the Transformer architecture, which uses self-attention mechanisms to address hierarchical structures in data.

- **Modern Large Language Models (LLMs)**: These are deep learning models trained on vast amounts of text data, using transformer architectures. They are capable of understanding and generating human-like text, and are often fine-tuned for specific applications through processes like supervised fine-tuning (SFT) and reinforcement learning from human feedback (RLHF).

## Trade-offs

Key trade-offs and limitations in Machine Learning include:
- **Data Dependence**: The performance of ML models heavily relies on the quality and quantity of training data. Insufficient or biased data can lead to poor model performance.

- **Model Interpretability**: Deep Learning models, while powerful, are often deemed “black boxes” because it can be challenging to understand exactly how they make decisions.

- **Computational Resources**: Deep Learning, especially, requires significant computational resources, making it more challenging for smaller-scale or resource-constrained environments.

## See also
- Artificial Intelligence
- [[deep-learning]]
- Supervised Learning
- Unsupervised Learning
- [[convolutional-neural-networks]]
- [[recurrent-neural-networks]]
- [[transformer]]
- [[large-language-models]]