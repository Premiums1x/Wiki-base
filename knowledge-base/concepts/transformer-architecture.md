---
concept: transformer-architecture
entity_type: concept
aliases: ["transformer-arch", "transformer"]
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T09:45:57Z
---

## Definition
Transformer Architecture is a deep learning model introduced by Vaswani et al. in their seminal paper "Attention is All You Need" in 2017. It extends the basic principles of previous deep learning models to offer a new way of processing information re-lstm which does not follow the sequential order necessary for traditional recurrent neural networks (RNNs). This architecture is built on the foundation of the self-attention mechanism, allowing it to assign different levels of importance to different elements within a sequence, thus capturing relevant features for tasks such as language translation and text generation deep-learning without being constrained by sequence length.

## How it Works
The Transformer Architecture operates in two main sections: the encoder and the decoder. Each section consists of a stack of identical layers, each made up of a multi-head self-attention mechanism and position-wise feed-forward networks.

### Encoder
The encoder encodes the input sequence into a continuous vector representation. This is done in two steps:
1. **Self-Attention Mechanism**: In this step, each position in the sequence attends to all positions in the sequence, assigning weights to each position based on their relevance.
2. **Position-wise Feed-Forward Networks**: These apply a fully connected network to each position of the input sequence separately.

### Decoder
The decoder generates the output sequence by integrating the encoder's output. This process also includes the self-attention mechanism but with an added layer of attention over the encoder's output, referred to as 'encoder-decoder attention'. This allows the decoder to take into account the entire input sequence when generating each token.

In both sections, a residual connection is used between the input and the output of each sub-layer, followed by layer normalization. This setup helps to stabilize the training process and helps the model to learn to progressively transform the input.

### Innovations over RNNs
Unlike traditional RNNs that process input sequences sequentially, the Transformer architecture can process all positions in the input sequence in parallel due to its attention mechanism. This makes it significantly faster and easier to train on large datasets. Moreover, the position-wise feed-forward networks make the architecture more scalable and capable of handling longer sequences.

## Variants
Transformers have evolved and been adapted in various ways since their introduction. Some key variants include:
- **GPT (Generative Pre-trained Transformer)**: Iterations of GPT are primarily focused on language understanding and generation gpt-family. They pre-train a large language model and then fine-tune it on tasks such as text completion, question-answering, and summarization.
- **BERT (Bidirectional Encoder Representations from Transformers)**: BERT builds on the Transformer architecture by using a masked language modeling objective and a next sentence prediction task for bidirectional training bert. This design allows BERT to capture more contextual information compared to uni-directional models.

## Trade-offs
While Transformer models are powerful and have enabled significant advances in natural language processing tasks, they also come with a set of trade-offs:
- **Resource Intensive**: Training Transformer models requires substantial computational resources due to the vast number of parameters overparameterization.
- **Training Time**: The training process can be very time-consuming, even with powerful hardware. This is exacerbated by the need for large datasets to achieve good performance.
- **Memory Consumption**: The self-attention mechanism relies on storing the entire input sequence, which consumes a lot of memory. This poses a challenge when working with longer documents or in real-time scenarios.

## See also
- re-lstm
- re-contex-policy (Related to reinforcement learning techniques used in fine-tuning and scaling, often trading off with the complexity of the initial model)
- deep-learning
- gpt-family