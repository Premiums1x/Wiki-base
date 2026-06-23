---
concept: machine-learning
entity_type: concept
aliases: ["ml"]
sources: ["raw\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-23T04:11:48Z
---

## Definition
Machine Learning (ML) is a branch of artificial intelligence (AI) that focuses on developing algorithms and statistical models that enable computers to improve their performance on a specific task with experience. Machine Learning builds on [[ai]] by automating the learning process so that a system can learn, identify, and adjust to patterns without being explicitly programmed.

## How it works
Machine Learning operates primarily through the use of algorithms and statistical models that parse data, learn from it, and then apply what they have learned to make informed decisions and predictions. This learning process generally involves the following steps: 

### Data Input
The algorithm starts by receiving data as input, which can be in various forms, such as images, texts, sounds, numerical statistics, geographical coordinates, or even binary messages.

### Feature Selection
Feature selection is the process of identifying and selecting those attributes of the data that are likely to be effective predictors of the target variable(s).

### Training Phase
The machine learning model is trained using algorithms which apply statistical learning methods to the input data to recognize patterns and make decisions. This phase may involve either a supervised learning process, where the data includes pre-defined categories or labels, or an unsupervised learning process, which explores data to find hidden patterns.

### Evaluation
Once trained, the model’s effectiveness is evaluated using metrics such as accuracy, precision, recall, and F1 score. The evaluation phase can be conducted through methods like cross-validation.

### Prediction Phase
Finally, the trained model is used to make predictions or classifications from new, unseen data. 

#### Supervised Learning
In supervised learning, the dataset is labeled with the correct answers for the problem to solve. The machine learning model is then trained to predict the correct label given the features of the data. Some common algorithms in supervised learning include support vector machines for classification, and linear regression for regression problems.

#### Unsupervised Learning
Unsupervised learning deals with data that has no known labels. The goal is to analyze the features of the input data and find hidden patterns, such as through clustering or dimensionality reduction techniques.

#### Semi-Supervised Learning
This approach attempts to use a small amount of labeled data and a large amount of unlabeled data for training the model. It builds on machine learning by leveraging both labeled and unlabeled data to improve learning results.

#### Reinforcement Learning
Reinforcement learning is a type of ML where an agent learns to make decisions by taking actions in an environment to achieve a goal. The agent receives rewards or penalties for specific actions.

## Variants
Machine Learning encompasses a variety of techniques:

- Traditional Machine Learning: includes decision trees, random forests, SVM, and others which treat data in a structured manner and are often mathematically derived solutions.

- Deep Learning: builds on neural networks and specifically artificial neural networks (ANN), which simulate the human brain's neural activity. Techniques like convolutional neural networks (CNN), long short-term memory (LSTM) networks, and the transformer architecture, which is relativelift-optimized, dominate this field.

- Large Language Models (LLMs): These are deep learning models with billions of parameters, trained on vast amounts of text data. They are enhanced through fine-tuning and retrieval-augmented generation (RAG), an approach that requires external knowledge bases.

## Trade-offs
Machine Learning models require a significant amount of high-quality data, computational power, and time to train effectively. One major trade-off with ML is the balance between model performance and complexity. More complex models, while potentially offering higher accuracy, also risk overfitting, where the model performs well on training data but poorly on unseen data. 

Another significant trade-off is the reliance on labeled data in supervised learning, which can be costly and time-consuming to prepare. Moreover, the interpretability of the model can be low, especially with deep learning models, making it difficult to understand the reasoning behind the model's predictions. 

Machine Learning also depends on a robust data cleaning and preprocessing pipeline, which can be a bottleneck in practical applications.