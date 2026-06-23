---
concept: recurrent-neural-network
entity_type: technique
aliases: ["循环神经网络", "RNN"]
sources: ["raw\\ai_machine_learning.md"]
confidence: high
created_at: 2026-06-23T06:33:28Z
---

## Definition
A Recurrent Neural Network (RNN) is a type of artificial neural network designed to handle sequential data by maintaining a hidden state that carries information from previous time steps. This hidden state is updated at each step and fed back into the network, allowing the RNN to selectively pass and retain information that helps predict the next elements in the sequence. It extends the traditional feedforward neural network by adding connections between the same set of neurons over successive layers, making it more suitable for processing data with temporal dependencies such as language, time series, and audio signals.

## How it works
At each time step \( t \), an RNN takes an input \( x_t \) and the previous hidden state \( h_{t-1} \). It combines these to produce a new hidden state \( h_t \) and an output \( y_t \) if applicable. The computation can be summarized by the following equations:

\[ h_t = f(W_{hh}h_{t-1} + W_{xh}x_t + b_h) \]
\[ y_t = g(W_{hy}h_t + b_y) \]

Where:
- \( W_{hh} \) are the weights connecting hidden layers.
- \( W_{xh} \) are the weights connecting inputs to the hidden layer.
- \( W_{hy} \) are the weights connecting the hidden layer to the output layer.
- \( b_h \) and \( b_y \) are biases for the hidden and output layers, respectively.
- \( f \) and \( g \) are activation functions, often chosen to introduce non-linearity into the model, such as the hyperbolic tangent (tanh) or rectified linear unit (ReLU).

The non-linear activation functions are crucial as they enable the RNN to learn complex patterns and relationships within sequences. However, vanilla RNNs suffer from issues such as the vanishing gradient problem, which can lead to difficulty in learning long-term dependencies in the data. Variants like the Long Short-Term Memory (LSTM) network and the Gated Recurrent Unit (GRU) have been proposed to mitigate these problems by introducing mechanisms for better retention and control of information flow within the network. LSTM, in particular, builds on the concept of the RNN by adding memory cells and gates (input, forget, and output gates) to better manage the flow of information across different time steps, thereby significantly improving its performance on tasks requiring a long-term memory, such as speech recognition and translation.

## Variants
### Long Short-Term Memory (LSTM)
LSTM enhances RNNs by including a cell state and three gates (input, forget, and output gates), which allow for more controlled information flow. This architecture addresses the vanishing gradient problem, enabling effective learning of dependencies in sequences that span long time intervals.

### Gated Recurrent Unit (GRU)
GRU optimizes the LSTM by merging the cell state and hidden state into a single state and combining the input and forget gates into a single update gate. This simplification reduces the number of parameters and computational overhead while retaining the ability to learn long-term dependencies.

### Bi-Directional RNN (BRNN)
In contrast to a standard RNN which processes a sequence of inputs in a single direction from start to finish, a BRNN processes the sequence in both forward and backward directions. This dual processing is useful for tasks where the context from both past and future relevant time steps should inform the network.

## Trade-offs
The primary trade-offs associated with RNNs stem from their inherent challenges in training and memory management:
- **Computation Cost**: The feedback connections in RNNs can significantly increase training time and resource consumption, especially with longer sequences.
- **Vanishing Gradient Problem**: Standard RNNs are prone to gradients diminishing as they are backpropagated through time, making it difficult to learn relationships far back in the sequence.
- **Memory Requirement**: RNNs, particularly with deep architectures, can have substantial memory needs due to the propagation of the hidden state across time steps.
- **Lack of Natural Order Handling**: Unlike transformers, standard RNNs process sequences sequentially from start to finish, which can limit their efficiency in some contexts, such as handling very long sequences where the order of processing can significantly impact the final output.

## See also
- long-short-term-memory
- gated-recurrent-unit
- [[transformer-architecture]]