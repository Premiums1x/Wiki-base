---
concept: recurrent-neural-networks
entity_type: technique
aliases: ["rnn"]
sources: ["raw/ai_machine_learning.md"]
confidence: high
created_at: 2026-06-23T03:36:43Z
---

## Recurrent Neural Networks (RNNs)

### Definition
Recurrent Neural Networks (RNNs) are a type of artificial neural network designed to process sequences of data, such as time series or sentences. Unlike traditional feedforward networks, RNNs possess internal memory that allows them to consider the context of previous inputs when processing new data, making them particularly useful for tasks involving sequential information.

### How it Works
RNNs operate by feeding the input sequence through a series of network layers. Each layer takes the current input along with the output from the previous layer as input. This recursion enables the network to maintain an "internal state" that acts as a form of memory, able to capture dependencies over varying time steps in the sequence. Thus, when processing input at time step t, the network can consider what it has learned from the previous time steps.

Formally, the output (or hidden state) at time step \( t \), denoted as \( h_t \), is computed as:
\[
h_t = f(x_t, h_{t-1}, \theta)
\]
where \( x_t \) is the input at time \( t \), \( \theta \) are the model parameters, and \( f \) is a function representing the network architecture. The decision to pass the previous hidden state to the next step is what gives RNNs their "recurrence" property.

### Variants
- **LSTM (Long Short-Term Memory)**: An improved RNN variant designed to alleviate long-term dependency problems by incorporating a mechanism for selectively remembering and forgetting information. LSTMs have a complex cell structure with gates (input, forget, and output gates) that help the network decide what to retain and what to discard from the internal state.
- **GRU (Gated Recurrent Unit)**: A simpler variant of LSTM, also designed to handle long-term dependencies. GRUs combine the forget and input gates into a single "update gate" and merge the cell state and hidden state, thereby reducing the number of gates and thus the complexity compared to LSTMs.

### Trade-offs
- **Advantages**: 
  - **Memory**: RNNs can store information over long sequences, making them ideal for tasks requiring context, such as language modeling and speech recognition.
  - **Efficiency**: They can handle sequences of arbitrary lengths, unlike feedforward networks that require a fixed-size input.
  
- **Limitations**:
  - **Vanishing/Exploding Gradients**: During training, gradients can diminish or grow exponentially over time steps, making long-term information hard to propagate. This issue is particularly prominent in simple RNNs.
  - **Complexity**: LSTMs and GRUs, while more effective at handling long sequences, are more complex and computationally expensive to train compared to simple RNNs.

### See also
- Artificial Neural Network
- [[deep-learning]]
- Supervised Learning
- Transformers