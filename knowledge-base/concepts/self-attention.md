---
concept: self-attention
entity_type: concept
aliases: ["scaled dot-product attention"]
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T08:00:46Z
---

## Definition
Self Attention is a mechanism within neural networks which enables the model to weigh the significance of different parts of input data, such as words in a sentence, by assigning higher weights to more relevant parts. This technique is pivotal in deep learning architectures due to its ability to capture contextual information efficiently without the need for sequential processing steps.

## How it works
In traditional feed-forward neural networks, each layer processes data in a sequential manner, often leading to a loss of context if the input is not inherently sequential. Self Attention, however, operates by processing the same input data at each position through a mechanism known as the attention mechanism. This mechanism calculates the importance of different parts of the input relative to each other and allows the model to focus on the most relevant information for each position.

The Self Attention mechanism works by first projecting input data into three different spaces: query, key, and value. For each input element (e.g., a word in a sentence), the model generates a query vector, a key vector, and a value vector. These vectors are used to compute a weighted score between each element and all elements in the sequence. Specifically, the formula to calculate the score is: 
\[ \text{Score} = \frac{\text{Query} \cdot \text{Key}^\top}{\sqrt{d_k}} \]
where \(d_k\) is the dimension of the key vectors. The dot product of the query and key vectors is scaled by \( \frac{1}{\sqrt{d_k}} \) to further normalize the dot product. This score reflects the relevance of the key with respect to the query. The scores are then passed through a softmax function to produce weights which are used to combine the value vectors in a weighted sum. This results in a new representation of the input that is sensitive to the interdependencies among the elements.

The attention weights are then utilized to compute a weighted sum of the value vectors: 
\[ \text{Attention}(Q,K,V) = \text{softmax}(\frac{QK^\top}{\sqrt{d_k}})V \]
This mechanism is iterated across the entire input data sequence, allowing the model to consider every word's context dynamically, as opposed to considering context statically or hierarchically.

Self Attention builds on the concept of attention mechanisms, which were initially designed to enable the model to focus on different parts of input information when processing sequences. It is part of the transformer architecture, which is a neural network architecture designed for sequence modeling that avoids the use of recurrence and convolutions. Transformers completely replace traditional recurrent neural networks (RNNs) due to their superior performance in handling long-range dependencies and parallelization capabilities.

## Variants
Variants of Self Attention include:
- **Multi-Head Attention**: This variant allows the model to jointly attend to information from different representation subspaces at different positions. It does this by generating multiple types of attention maps simultaneously. Each map learns to attend to a separate set of positions, and then the aggregated outputs are concatenated and projected.
- **Layer Normalization**: This technique normalizes the activations of every layer and can improve the training speed and stability of the model, particularly when used in conjunction with Self Attention.
- **Position-wise Feed-Forward Layer**: Follows the attention layers to provide further non-linear processing for each position.

These variants extend the basic Self Attention mechanism to enhance the representational power and efficiency of the models.

## Trade-offs
Self Attention, while highly effective, introduces certain trade-offs and considerations:
- **Memory Footprint**: The computational cost of evaluating the attention mechanism is proportional to the square of the input sequence length, making it less efficient for very long sequences. This can be mitigated by employing techniques such as local-attention, which only considers a local context around each token.
- **Context Understanding**: Self Attention mechanisms can capture long-range dependencies, but they can struggle in certain contexts where the dependencies are more complexly structured or require sequential processing. Models that depend on RNNs or its variants might still be preferred in scenarios where the sequential order matters fundamentally.

Self Attention trades off the sequential processing of traditional RNNs for a parallelizable mechanism that captures long-range dependencies efficiently.

## See also
- transformer
- recurrent neural network
- local-attention