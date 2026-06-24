---
concept: finetuning
entity_type: technique
aliases: ["sft", "rlhf"]
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T09:46:08Z
---

## Definition

Finetuning is a process in machine learning where a pre-trained model is adjusted with a smaller dataset that is specific to the task at hand. This approach leverages transfer-learning, which builds on the fact that a model trained on one task can adapt to perform another task more efficiently than starting from scratch. Finetuning is particularly useful in scenarios where a large amount of labeled data is scarce.

## How it works

The process of finetuning involves several steps. Initially, a pre-trained model, usually a deep learning network like a Transformer architecture, is fine-tuned on a smaller dataset specific to the desired application. This is typically done by applying a different loss function that is more relevant to the new task than what was used during the original pre-training phase. For example, when modifying a model from processing a general language corpus to performing specific tasks such as sentiment analysis or question-answering, the model must be adjusted to optimize for these different tasks.

During finetuning, the model's parameters are updated, often with fewer layers frozen and more layers left trainable. This ensures that the early layers, which contain more generic features extracted from the pre-training phase, can still be beneficial to the new task. Similarly, the learning rate typically starts lower than that used in pre-training to avoid disruptive changes to the existing knowledge within the model.

One of the key applications of finetuning is in refining language models, as seen in the context of large language models (LLM) like GPT-4. These models are initially pre-trained on vast amounts of text through unsupervised learning, and then finetuned using supervised learning and reinforcement learning with human feedback (RLHF). This process is crucial for aligning the model's outputs with human preferences without necessarily having extensive labeled data for the new task. Additionally, finetuning can incorporate retrieval-augmented hybrid models (RAG), where supplementary information from external knowledge bases is retrieved to enhance the model's output.

## Variants
- **RLHF (Reinforcement Learning with Human Feedback)**: An implementation of finetuning that relies on human feedback to refine a model's behavior. It involves fine-tuning a model on data where human judgments are used as rewards for policy learning, making the model's responses more aligned with common human preferences.
- **SFT (Supervised Fine-Tuning)**: An alternative to reinforcement learning in finetuning, where models are directly supervised with labeled data rather than learning to optimize a reward function based on human feedback. SFT is simpler and more straightforward but may limit the diversity of user responses due to its reliance on explicit supervision.

## Trade-offs
Finetuning, while highly effective for leveraging pre-existing models, also has some significant trade-offs:
1. **Generalization vs. Specificity**: There is a balance to be struck between exploiting general knowledge (carried over from the pre-trained model) and adapting to the specific nuances of a new task. Too much generalization can dilute the model's performance on the specific task, while overfitting to new data can lose potentially useful aspects of the pre-training phase.
2. **Data Requirements**: Finetuning still requires some amount of task-specific data, which can be a bottleneck if such data is expensive to acquire or scarce. On the other hand, pre-training requires a massive amount of data, which is easier to come by.

## See also
[[supervised-learning]], [[unsupervised-learning]], reinforcement-learning, transfer-learning, pre-training