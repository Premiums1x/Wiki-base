---
concept: artificial-intelligence
entity_type: concept
aliases: ["人工智能"]
sources: ["raw\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-23T06:32:50Z
---

## Definition
Artificial Intelligence (AI) is the scientific and engineering endeavor aimed at equipping machines with the ability to exhibit human-like intelligence. It encompasses a broad range of algorithms, techniques, and methodologies designed to simulate cognitive functions such as learning, reasoning, problem-solving, perception, and understanding. Machine Learning ([[machine-learning]]) builds on AI, focusing on creating systems that can learn from data and experience without being explicitly programmed.

## How It Works
AI operates on a spectrum from simple rule-based decision-making to complex cognitive tasks. The key processes forming the backbone of AI include:

### Machine Learning
Machine Learning (ML) extends AI by enabling algorithms to improve and adapt through experience and data. ML's objective is to develop algorithms that can automatically perform predictive tasks by learning from existing data, thereby reducing the need for manual programming.

#### Traditional Machine Learning
Traditional ML methods often involve structured data and utilize statistical models to make predictions. These methods include:

- **Supervised Learning**: This approach builds models based on input data for which the output is known. The system learns from labeled data to predict outcomes accurately. Common tasks include classification and regression.
- **Unsupervised Learning**: Here, the model learns from datasets without labels, discovering hidden patterns and relationships. Common tasks are clustering and dimensionality reduction.

#### Deep Learning
Deep Learning (DL) represents an advanced form of ML that relies on artificial neural networks (ANNs), which mimic the structure and function of biological neurons. Deep Learning algorithms have multiple layers, each processing and extracting features from data, leading to sophisticated learning mechanisms. Techniques like Convolutional Neural Networks (convolutional-neural-networks) excel in processing image and video data, while Recurrent Neural Networks (recurrent-neural-networks) and Long Short-Term Memory (LSTM) networks are particularly effective for sequence data such as natural language texts and time-series data. Transformer architecture, which features self-attention mechanisms, is at the forefront of modern AI, revolutionizing the field of Natural Language Processing (natural-language-processing).

### Modern Large Language Models (LLMs)
Large Language Models (LLMs) are advanced DL models that are pre-trained on massive amounts of text data, forming the basis for applications like GPT-4 and Claude. These models are initialy trained in an unsupervised manner through self-supervised learning, aiming to predict the next token in a sequence of words. Post-pretraining, fine-tuning and reinforcement learning from human feedback (RLHF) are applied to refine the model's output according to human preferences.

## Variants
AI encompasses a wide array of methodologies and techniques, each designed to tackle different aspects of intelligence. These include but are not limited to:

- **Rule-Based Systems**: Systems that make decisions based on pre-defined rules.
- **Neural Networks**: Systems modeled after the human brain, capable of learning from examples.
- **Decision Trees**: A method that creates a model to predict the outcome of an event based on several features.
- **Support Vector Machines (SVMs)**: Algorithms used for classification and regression analysis.
- **Natural Language Processing**: Processing human language data in a form that can be analyzed by computer programs, which optimizes AI's capability to interact effectively with human users.

## Trade-offs
While AI offers significant advantages, it also comes with notable trade-offs, limitations, and considerations:

- **Data Privacy and Security**: AI systems, especially those dealing with sensitive data, raise concerns about data privacy and security. These systems depend on collecting vast amounts of user data, which can potentially be misused.
- **Transparency and Explainability**: Many advanced AI models, such as deep neural networks, are often a black box; they are highly effective but provide little insight into their decision-making processes, making debugging and improvement challenging. 
- **Bias and Fairness**: AI models can inherit biases from the data on which they are trained. These biases can then perpetuate societal inequalities if not properly mitigated.
- **Energy Consumption**: Training large deep learning models can be extremely resource-intensive, both in terms of computation and energy usage.

## See also