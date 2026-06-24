---
concept: ai-aim-machine-learning
entity_type: concept
aliases: []
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T09:44:53Z
---

## Definition
Artificial Intelligence (AI) is a scientific and engineering endeavor aimed at creating or programming systems to perform tasks that typically require human intelligence. Machine Learning (ML) is a subfield of AI that focuses on designing algorithms that allow systems to learn patterns from data, making them capable of performing tasks without explicit programming. Within this suite of technologies, deep-learning builds on machine learning, utilizing multi-layer neural networks to achieve more complex and nuanced learning capabilities.

## How it works
### Traditional Machine Learning
Traditional machine learning typically involves structured data and utilizes statistical and mathematical techniques to train models.

#### Supervised Learning
Supervised learning uses datasets that are labeled with the desired output. The goal is to infer a function from labeled training data, enabling the model to predict the output for new, unseen inputs.

1. **Classification**: One common task involves predicting categorical labels. Algorithms like Support Vector Machines (SVM), Decision Trees, and Random Forest are prominent for this purpose.
2. **Regression**: Predicting continuous values, such as predicting house prices, involves algorithms like Linear Regression.

#### Unsupervised Learning
Unsupervised learning does not rely on labeled data and aims to extract meaningful structure from the input. Key tasks include:

1. **Clustering**: Grouping similar instances together. A popular algorithm is K-Means.
2. **Dimensionality Reduction**: Reducing the number of random variables under consideration, often by condensing redundant data features. Principal Component Analysis (PCA) is frequently employed.

### Deep Learning
Deep Learning extends traditional ML by employing artificial neural networks, which mimic the human brain's structure with many layers of connected nodes. These networks excel at learning from large datasets and complex data structures.

1. **Convolutional Neural Networks (CNNs)**: Specifically designed for image and video data, CNNs leverage convolution operations to capture spatial hierarchies within data.
2. **Recurrent Neural Networks (RNNs)** and Long Short-Term Memory networks (LSTMs): These networks are adept at processing sequential data, like text and speech.
3. **Transformer Architectures**: This modern approach introduces the self-attention mechanism, significantly improving the handling of sequences over traditional RNNs and deep-learning techniques.

### Modern Large Language Models (LLMs)
Large Language Models (LLMs) such as GPT-4, Claude, Gemini, and DeepSeek are massive neural network models designed for understanding and generating human-like text.

1. **Pre-training**: Involves training the model on vast amounts of unlabelled data to learn general knowledge and linguistic structures through unsupervised learning.
2. **Fine-tuning and Reinforcement Learning from Human Feedback (RLHF)**:
    - **Supervised Fine-tuning (SFT)**: Enhances the model’s performance on specific tasks using labeled data.
    - **Reinforcement Learning from Human Feedback (RLHF)**: Ensures the model aligns with human values by adjusting its behavior based on human preferences.
3. **Retrieval-Augmented Generation (RAG)**: Integrates external knowledge bases during inference, complementing the model’s internal knowledge to ensure accurate and contextually relevant responses.

## Variants
Several variants of AI and ML exist each with its advantages and use cases:

* **Reinforcement Learning**: A type of ML where the model learns to make decisions by receiving rewards or penalties for its actions.
* **Bayesian Machine Learning**: This approach incorporates a probabilistic framework, optimizing prediction accuracy by integrating statistical inference and experimental data.
* **Transfer Learning**: A technique in which a model trained on one task is fine-tuned to perform another, closely related task, offering significant computational benefits.

## Trade-offs
Big models and complex learning algorithms often come with their share of challenges:

- **Computational Demands**: LLMs and deep models require substantial computational resources and time for both training and inference. This can be particularly costly for enterprises.
- **Data Requirements**: To achieve high performance, these models need abundant, high-quality data. Acquiring and labeling such data represent significant challenges.
- **Explainability and Transparency**: Black-box models like deep-learning can be difficult to interpret, which might be problematic in sectors requiring a level of transparency, such as healthcare.
  
Moreover, these models tend to exhibit a trade-off in performance versus interpretability. As the complexity of models increases with depth, it often becomes harder to understand how predictions are made, which can hinder practical application and trust.

## See also
[[supervised-learning]]
[[unsupervised-learning]]
deep-learning
natural-language-processing