---
concept: transformer
entity_type: technique
aliases: []
sources: ["raw/ai_machine_learning.md"]
confidence: high
created_at: 2026-06-23T03:37:09Z
---

## Definition

A Transformer is a deep learning architecture introduced in the paper "Attention is All You Need" by Vaswani et al. in 2017. It is a neural network that relies on self-attention mechanisms to process input sequences in parallel, enabling it to handle tasks such as natural language processing (NLP) and sequence modeling more efficiently than traditional architectures like Recurrent Neural Networks (RNNs) and Convolutional Neural Networks (CNNs).

## How it works

### Core Components

1. **Self-Attention Mechanism**:
   - **Query, Key, and Value**: The Transformer computes query, key, and value vectors for each position in the input sequence. These are then used to compute attention scores, which indicate the relevance between positions.
   - **Scaled Dot-Product Attention**: Computes the attention score as the dot product between the query and key vectors, scaled by the square root of the key vector’s dimension, and then applying a softmax function to normalize the scores.
   - **Multi-Head Attention**: Allows the model to jointly attending to information from different representation subspaces at different positions.

2. **Feed-Forward Network**:
   - Each position in the sequence generates new values through a fully connected feed-forward network, which is applied independently to each position.

3. **Positional Encoding**:
   - Since the self-attention mechanism is position-agnostic, the Transformer adds specific positional encodings to the input embeddings to impart the sequence information.

### Structure and Steps

1. **Input Embeddings**: Tokenize inputs and embed them into a high-dimensional space.
2. **Add Positional Encoding**: Combine embeddings with positional encodings.
3. **Encoder Blocks**:
   - **Self-Attention Layer**: Attention mechanism across the entire input sequence.
   - **Feed-Forward Layer**: Processing individual positions using a fully connected network.
   - **Normalization and Addition**: Layer normalization followed by residual connections.
4. **Decoder Blocks**: Similar to the encoder but also includes an attention mechanism over the encoder output.
5. **Output**: Softmax layer on top of the final encoder/decoder block for predictions.

## Variants

1. **BERT (Bidirectional Encoder Representations from Transformers)**: Uses the Transformer to pre-train a language model by masking parts of the input and predicting those masked tokens.
2. **GPT (Generative Pre-trained Transformer)**: Trains the Transformer in an autoregressive manner, predicting the next token based on the previous tokens.
3. **T5 (Text-to-Text Transfer Transformer)**: Frames all NLP tasks as text-to-text tasks, unifying them under a single Transformer architecture.
4. **Vision Transformers (ViT)**: Applies the Transformer to the domain of image recognition, treating images as sequences of patches.

## Trade-offs

### Key Limitations
- **Computational Complexity**: The self-attention mechanism can be computationally expensive and memory-intensive, especially for long sequences.
- **Long-Range Dependencies**: While self-attention can theoretically capture long-range dependencies, the squared complexity (relative to sequence length) may limit its practical efficiency.
- **Training Cost**: Pre-training large Transformers on large datasets requires significant computational resources and time.

### Considerations
- **Parameter Efficiency**: Attention mechanisms allow the model to focus on relevant parts of the input efficiently.
- **Parallel Computation**: Unlike RNNs, Transformers allow for parallel processing of sequence elements, significantly speeding up training.
- **Transfer Learning**: Transformers can leverage pre-trained models effectively for a variety of downstream tasks with fine-tuning, reducing the requirement for task-specific training data.

## See also
[[deep-learning]], [[recurrent-neural-networks]], [[convolutional-neural-networks]], Natural Language Processing