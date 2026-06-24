---
concept: recurrent-neural-network
entity_type: concept
aliases: ["rnn"]
sources: ["raw\\01-ai-and-machine-learning\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-24T09:45:46Z
---

## Definition
A Recurrent Neural Network (RNN) is a deep learning model architecture used to handle sequential or time-series data. Unlike traditional feedforward networks, where information flows only in one direction, RNNs utilize feedback loops to retain information from previous inputs in their memory for processing the current input. This self-feedback mechanism extends and builds on the basic concept of feedforward networks by allowing the network to maintain a form of stateful memory useful for sequence modeling tasks.

## How it works
RNNs operate by transforming an input sequence into a feature representation and feeding it through hidden layers with feedback connections. Each node in the network, except the output layer, has an input and an explicitly defined output to the next time step. This architecture is designed to handle varying input lengths and capture temporal dependencies, which is crucial for tasks involving sequences, such as natural language wikilink: natural-language-processing.

In an RNN, a hidden state (\(h_t\)) at each time step \(t\) is a function of the previous hidden state \(h_{t-1}\) and the current input \(x_t\). Mathematically, this can be expressed as:

\[ h_t = \text{f}(h_{t-1}, x_t) \]

where \(\text{f}\) is the activation function applied to the linear combination of the previous state and the current input. This mechanism enables the network to make decisions in the current step based on past inputs, making it well-suited for tasks involving sequence predictions, such as language modeling or time-series forecasting.

However, traditional RNNs suffer from the vanishing gradient problem, where gradients get smaller as they are backpropagated through time, making it hard for the network to learn dependencies over larger sequences. To address this, variations like Long Short-Term Memory (LSTM) networks and Gated Recurrent Units (GRUs) were introduced. These extend RNNs by incorporating gates or other mechanisms to better control the flow of information and mitigate the vanishing gradient issue.

## Variants
Several variants of RNNs are designed to address the limitations of the basic architecture:

1. **Long Short-Term Memory (LSTM)**: This optimization improves upon traditional RNNs by introducing memory cells and three types of gates (input, forget, and output gates) to control the information flow. This design allows for the learning of dependencies over longer sequences without the vanishing gradient problem.

2. **Gated Recurrent Unit (GRU)**: GRUs offer a more compact architecture that optimizes LSTM by combining the forget and input gates into a single update gate. This simplification reduces the number of parameters and often provides comparable performance to LSTM with fewer computational requirements.

3. **Transformer Networks**: While not a direct variant of RNNs, Transformer networks have become prevalent due to their effectiveness in handling sequential data, especially in natural language processing (NLP) tasks. They do not require sequential processing and instead use self-attention mechanisms, trading off some of the temporal dependencies handling of RNNs with the ability to efficiently process data in parallel.

## Trade-offs
RNNs and their variants face various trade-offs when handling sequential data:
- **Complexity and Computational Cost**: The introduction of gates in LSTM and GRU networks significantly increases the model complexity and, consequently, the computational cost. This can make these models slower and harder to train compared to simpler RNNs.
- **Memory Usage**: RNNs and their variants can require large amounts of memory, especially for longer sequences, as they need to maintain hidden states for all past inputs.
- **Hardware Requirements**: The parallel computing capabilities of RNNs and their variants are limited, unlike Transformer networks which are optimized for use with GPUs and modern parallel computing architectures. This dependency on powerful hardware can be a limiting factor for deployment in resource-constrained environments.



## See also
wikilink: natural-language-processing
wikilink: deep-learning